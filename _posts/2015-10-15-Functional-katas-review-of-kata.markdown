Functional Kats: Kata review
```
{highlight FSharp}

let isPrime x =
    match x with
    | 2 | 3 -> true
    | x when x % 2 = 0 -> false
    | _ ->
        let rec superPrimeCheck i =
            match i with
            | i when x % i = 0 -> false
            | i when x < i*i -> true
            | _ -> superPrimeCheck (i + 2)
        superPrimeCheck 3

isPrime 1
let oneM = 1000000
let checkStuff maxNumber =
            [2..10000]
            |> Seq.ofList
            |> Seq.filter(fun x-> isPrime x)
            |> Seq.fold(fun acc x ->                                                                                    
                            if (isPrime acc && acc <= maxNumber)then
                                printfn "found %A" acc
                            acc + x                            
                            ) 0
{endhighlight }
```


Choose sequences because:.

* A `seq<'a>` computes on demand, so even tho we are not doing this here, maybe that can be a possible way to optimise this code?
* Side effects happen when the value is consumed
* the yield of a sequence expression can also be another sequence, signified through the use of the `yield!` keyword
