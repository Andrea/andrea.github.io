---
author: roundcrisis
date: 2020-08-15 20:48:00+00:00
layout: post
title: Running scala steward locally
categories:
- scala
- dependencies
- scala-steward
---

## Running scala steward locally

### Motivation

Keep the dependencies in many repositories up to date as automatically as possible. Warn me when they can't be updated automatically without breaking the build.

### How to run

You can run by clonning the repo and running it, check the [instructions](https://github.com/scala-steward-org/scala-steward/blob/master/docs/running.md).If you want to run this on private repos on some CI I find that it might be easier to run from Docker. I especially like that you can use a particular version you know works and move when you are ready.

To run from Docker, execute something like this from where you checked out scala-steward(setup the necessary env vars STEWARD_DIR, LOGIN and EMAIL accordingly):

```
docker run -v $STEWARD_DIR:/opt/scala-steward -it fthomas/scala-steward:latest \
  --workspace  "/opt/scala-steward/workspace" \
  --repos-file "/opt/scala-steward/repos.md" \
  --default-repo-conf "/opt/scala-steward/default.scala-steward.conf" \
  --git-author-email ${EMAIL} \
  --vcs-api-host "https://api.github.com" \
  --vcs-login ${LOGIN} \
  --git-ask-pass "/opt/scala-steward/.github/askpass/$LOGIN.sh" \
  --sign-commits \
  --env-var FOO=BAR
```


Let's break this down

The first few options are for docker to run and mount the current directory as a volume then there is the scala steward options:

* workspace: where all the repos will be cloned, etc.
* repos-file: This is a file with a format like ` - user/repo` per line. These are the repos you are asking scala steward to keep up to date.
* default-repo-conf: This is an optional argument. I haven't used this but seems to be about pull request frequency, commit messages, etc.
* git-author-email: The email that will be used in the commit.
* vcs-api-host: Generally it will be `"https://api.github.com"` the url of the api of the git host server. AFAIK github, gitlab and bitbucket supported so far.
* vcs-login: the username of the git account
* git-ask-pass: I found this kind of strange, and ~have to wonder about alternatives~ [this is why](https://github.com/scala-steward-org/scala-steward/issues/518). This is for the path to an script file that returns: the plain text password :( *or* an authentication token. The script must start with `!#/bin/sh`. For this, since running this internally, I create the file on the fly with information available in my CI environment, similar to what how it is described ine the link above. 
* sign-commits: I don't use this. Might be useful in case one wants to sign the commits.
* env-var: if you need to add any extra environment variables so that the repos run.


Now that you have Scala steward set up you might want to select a test repo to update. 
Before you add that to the `repos-file` set up pull request building in 
your CI or externally. There are many options here, I tested a jenkins plugin (it was painful and didn't work well in my case), Aws CodeBuild and Github Actions. The last two were pretty painless.

Optionally you might want to also set up [Mergify](https://mergify.io/) or something like that, to automatically merge certain PRs.


### Depdendency Management over time

So with PR building set up you might be tempted to add all your repos at once. That might be a bad idea. This tools creates one PR per change, it is very likely you might want to update many libraries at once. To know what is out of date you can simple use `sbt dependecyUpdates`
Also you don't want to block CI for a while (if that is your setup). I suggest you add a few repos at a time and see what happens. This is a good task to do while waiting for something else.

<img src="https://imgs.xkcd.com/comics/compiling.png" >


Since not so long ago *Scalafix* updates enabled by default, also you can add your custom scalafix changes.

Please note, you can set up configuration per project if you want to stop particular updates.

### Some other ways

Since this is all about managing dependencies, these are some interesting projects that I am planning to check out(but haven't yet):

* [sbt-bobby](https://github.com/hmrc/sbt-bobby): You create a set of rules which outlaw particular versions of a library or plugin, and task Bobby to enforce those rules. If a violation is detected, the whistle is blown, and the build is failed.

* [Enforcing Consistent Versions of Third Party Dependencies](https://softwarecorner.wordpress.com/2020/06/30/a-simple-sbt-plugin-enforcing-consistent-versions-of-third-party-dependencies/) A blog post that describes a way to manage consistent dependencies using an sbt plugin. I think this works if the projects all have the same collection of deps.