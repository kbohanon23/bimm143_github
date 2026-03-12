# Class 6: R Functions
Kiana Bohanon (PID: A17802316)

- [Background](#background)
- [Our First Function](#our-first-function)
- [A Second Function](#a-second-function)
- [A Protein Generating Function](#a-protein-generating-function)

## Background

All functions in R have at least 3 things:

- A **name** that we use to call the function.
- One or more input **arguments**.
- The **body** the lines of R code that do the work.

## Our First Function

Let’s write a silly little function called `add()` to add some numbers
(the input arguments).

``` r
add <- function(x,y) {
  x+y
}
```

Now we can use this function:

``` r
add(100, 1)
```

    [1] 101

``` r
add(x=c(100,1,100),y=1)
```

    [1] 101   2 101

> Q. What if I give a multiple element vector to `x` and `y`?

``` r
add(x=c(100,1),y=c(100,1))
```

    [1] 200   2

> Q. What if I give three inputs to the function?

``` r
#add(x=c(100,1),y=1,z=1)
```

> Q. What if I give only one input to the add function?

``` r
addnew <- function(x,y=1) {
  x+y
}
```

``` r
addnew(x=100)
```

    [1] 101

``` r
addnew(c(100,1),100)
```

    [1] 200 101

If we write our function with input arguments having no default value,
then the user will be required to set them when they use the function.
We can give our input arguments “default” values by setting them equal
to some sensible value - e.g. y=1 in the `addnew()` function.

## A Second Function

Let’s try something more interesting: Make a sequence generating tool…

The `sample()` function can be a useful starting point here:

``` r
sample(1:10,size=4)
```

    [1] 10  4  7  2

> Q. Generate 9 random numbers taken from the input vector, x=1:10?

``` r
sample(1:10,size=9)
```

    [1] 10  9  6  8  7  1  5  2  3

> Q. Generate 12 random numbers taken from the input vector, x=1:10?

``` r
sample(1:10,size=12, replace=TRUE)
```

     [1]  8  3  1  1 10  4  6  2  8  5  4  6

> Q. Write code for the `sample()` function that generates nucleotide
> sequences of length 6?

``` r
sample(c("A","G","T","C"), size=6, replace=TRUE)
```

    [1] "G" "G" "G" "C" "C" "C"

> Q. Write a first function `generate_dna()` that returns a user
> specified length DNA sequence:

``` r
generate_dna <- function(x) {sample(c("A","G","T","C"), size=x,replace=TRUE)}
```

``` r
generate_dna(8)
```

    [1] "G" "G" "G" "C" "A" "A" "A" "A"

``` r
generate_dna(20)
```

     [1] "A" "T" "G" "C" "G" "C" "T" "C" "C" "A" "T" "T" "T" "A" "T" "A" "T" "T" "G"
    [20] "G"

> **Key Points** Every function in R looks fundamentally the same in
> terms of its structure. Basically 3 things: name, input, and body.

    name <- function(input) {body}

> Functions can have multiple inputs. These can be **required**
> arguments or **optional** arguments. With optional arguments having a
> set default value.

> Q. Modify and improve our function `generate_dna()` to return it’s
> generated sequence in a more standard format like “AGTAGTA” rather
> than the vector “A”, G”, “T”, “A”.

``` r
generate_dna <- function(x=6,fasta=TRUE) {
  ans <- sample(c("A","G","T","C"), size=x,replace=TRUE)
  if(fasta) {cat("Single element vector output") 
    ans <- paste(ans, collapse="")} else{cat("Multi-element vector output")}
  
   return(ans)}
generate_dna()
```

    Single element vector output

    [1] "GAAATC"

``` r
generate_dna(fasta=TRUE)
```

    Single element vector output

    [1] "CTCAAT"

The `paste()` function - it’s job is to join up or stick together
(a.k.a. paste) input strings together.

``` r
paste(c("alice"), "loves R", sep=" ")
```

    [1] "alice loves R"

Flow control means where the R brain goes in your code

``` r
good_mood <- FALSE

if(good_mood) {cat("Great!"
)} else{cat("Bummer!")}
```

    Bummer!

## A Protein Generating Function

> Q. Write a function, called `generate_protein()`, that generates a
> user specified length protein sequence.

``` r
generate_protein <- function(len) {
  aa <- c("A","C","D","E","F","G","H","I","K","L","M","N","P","Q","R","S","T","V","W","Y")
  ans <- sample((aa), size=len, replace=TRUE)
  ans <- paste(ans, collapse="")
return(ans)
}
# The amino acids to sample from
# Draw n=len amino acids to make the sequence
```

``` r
generate_protein(39)
```

    [1] "CCPQQAQNTTFVPYTKIGNNYNCFPYMNYTDSTRYKYQD"

> Q. Use that function to generate random protein sequences between
> length 6 and 12.

``` r
for(i in 6:12) {
 # FASTA ID line ">id"
   cat(">", i, sep="", "\n")
  # Our protein sequence line
  cat(generate_protein(i), "\n")
}
```

    >6
    LYAFPY 
    >7
    TDVEMDW 
    >8
    PDCPFWYE 
    >9
    DFAGNIMQQ 
    >10
    STWWMDMATS 
    >11
    AIVNVCWRSAL 
    >12
    HFHEPRIDPPAY 

> Q. Are any of your sequences unique i.e. not found anywhere in nature?

Sequences 9, 10, 11, and 12 are not found anywhere in nature, as they do
not have 100% percent identity and 100% query coverage.
