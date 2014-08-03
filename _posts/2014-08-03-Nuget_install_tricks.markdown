---
date: 2014-08-03 14:13:00
layout: post
title: NuGet install tricks
categories:
- programming 
- development

---

Recently I was finishing off the great work [Carsten](http://gettingsharper.de/) started on the Nunit addin for [FsCheck](https://github.com/fsharp/FsCheck) and I had to use a not very common feature of Nuget, running powershell scripts automatically on install.

Disclaimer: I don't like powershell, it is better than nothing, but every time I use is harder that it needs to be.

#### Running powershell scripts automatically when installing and removing packages

There are a few powershell files that run (if they exists on /tools in your package definition): Init.ps1 , install.ps1 and uninstall.ps1
Init.ps1 runs the first time a package is installed in a solution, install.ps1 runs when a package is installed in a project, uninstall.ps1 runs when removing the package. There more information about these files [here](http://docs.nuget.org/docs/creating-packages/creating-and-publishing-a-package) in the section called "Automatically Running PowerShell Scripts During Package Installation and Removal" 

#### The script

In the docs above, when you are looking at what you can do regarding project, it refers you to [this page](http://msdn.microsoft.com/en-us/library/51h9a6ew%28v=VS.80%29.aspx) hint there is no info about Object :/. Thankfully I was pointed towards SpecFlow's install.ps1 file:

https://github.com/techtalk/SpecFlow/blob/master/Installer/NuGetPackages/NUnit.Runners/Install.ps1


I ran into a little problem when building this, I had specified a path wrong on my script and this is the error I got:

{% highlight %}
 Exception calling "Add" with "1" argument(s): "Unspecified error
 (Exception from HRESULT: 0x80004005 (E_FAIL))" At

 + $project.Object.References.Add <<<< ($NunitRunners+"nunit.core.dll")
     + CategoryInfo          : NotSpecified: (:) [], MethodInvocationException
     + FullyQualifiedErrorId : ComMethodTargetInvocation
{% endhighlight %}

Just for completeness this is the final install.ps1

{% highlight PowerShell %}
param($installPath, $toolsPath, $package, $project)

write-host "Adding a reference to nunit.core and nunit.core.interfaces to the project"
$packagesFolder = Split-Path -Path $installPath -Parent
$version = ""

# Get-Package -Filter NUnit.Runners also returns packages with NUnit.Runners in the description (e.g. NUnit or SpecFlow.NUnit.Runners)
# we need to find the one, that we are looking for
$nunitPackages = Get-Package -Filter NUnit.Runners
foreach ($nunitPackage in $nunitPackages)
{
	# there is a bug in NuGet: the package id for all returned packages is "NUnit.Runners", so filtering that is not enough
	if ($nunitPackage.Id = "NUnit.Runners" -and $nunitPackage.ProjectUrl.ToString().Contains("nunit")) 
	{ 
		$version = $nunitPackage.Version.ToString() 
	}
}

if ($version -ne "") 
{ 
	$nunitPackageToolsLibFolder = $packagesFolder + "\NUnit.Runners." + $version + "\tools\lib\"
    
    write-host "The nunit location is: " + $nunitPackageToolsLibFolder
    
	$nunitCoreInterfacesRef = $project.Object.References.Item("nunit.core.interfaces")
	if ($nunitCoreInterfacesRef) { $nunitCoreInterfacesRef.Remove() }
	$project.Object.References.Add($nunitPackageToolsLibFolder + "nunit.core.interfaces.dll")
    
    $nunitCoreRef = $project.Object.References.Item("nunit.core")
	if ($nunitCoreRef) { $nunitCoreRef.Remove() }
	$project.Object.References.Add($nunitPackageToolsLibFolder + "nunit.core.dll")
}



{% endhighlight %}

I am writing this mostly because I didn't find many blog posts about this. 

#### Some other random NuGet features

I don't do a lot of nugeting(?) but there are a few features I think can be very useful:

* You can specify assemblies that will be referenced (and have more assemblies available on the files tag )
* You can use the content folder in the manifest and add files to the project you are installing the package. More info [here](http://docs.nuget.org/docs/reference/nuspec-reference) search for the **Content Files** section
* You can target different frameworks 

Till the next time.