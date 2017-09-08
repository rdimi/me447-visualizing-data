
elements of an Rmd report
-------------------------

Initialize an .Rmd file

-   Open a new Rmd file.
-   Save it in your *practiceR* directory with filename *tut-04\_second-report.Rmd*.
-   Delete everything below the YAML header.
-   Edit the title and name in the header.
-   For now, use HTML output.
-   Knit HTML to check that everything works as expected.

auto-date
---------

If you want the document date to auto-update, edit the YAML header date field to read:

<pre class="r"><code>date: "<code>`</code>r format(Sys.time(), "%Y-%m-%d")<code>`</code>"</code></pre>
The single backticks delimit executable in-line R code.

-   Knit HTML to check that everything works as expected.

setting code chunk behavior
---------------------------

The element after the header is a code chunk that specifies *knitr* settings that establish how you want the code chunks in this script to behave.

-   *Insert &gt; R* in the menu bar just above the file pane. This creates the R code chunk delimiters for you.

<pre class="markdown"><code>```{r}

<code>```</code></code></pre>
-   Inside the code chunk, add the following.

        # set the knitr working directory  
        library(knitr)  
        opts_knit$set(root.dir="../")  

These lines of code ensure that when you knit an .Rmd file in your *portfolio* directory, *knitr* treats the directory one level up (the main course directory) as the working directory.

This behavior then matches how the various R scripts you have been writing work. They all treat the main RStudio project directory (your course folder) as the working directory.

-   In the same code chunk, add these lines,

        # the output document prints the code  
        opts_chunk$set(echo = TRUE)  

These lines cause *knitr* to include the code in the code chunk as well as the code output in the document. If you don't want the code to be printed, set the argument to *FALSE.*

-   Knit HTML to check that everything works as expected.

prose
-----

-   Add a couple of paragraphs on any topic at all.
-   Add markup tags to make a word or phrase *italic*, another **bold.**
-   Knit HTML to check that everything works as expected.
-   Spellcheck using the F7 function key when your script pane is active.

code chunk
----------

Add a code chunk that reads and prints a data set. I'm assuming that from an earlier tutorial, you have the *DSR-table1.xlsx* file in your *data* directory.

``` r
library(readxl)
tidy_data <- read_excel(
       path = "data/DSR-table1.xlsx"
    , sheet = "DSR-table1"
    )
```

-   Knit HTML to check that everything works as expected.

simple table
------------

-   Add a code chunk that uses *kable()* to print a simple table.
-   Knit HTML to check that everything works as expected.

``` r
library(knitr)
kable(tidy_data)
```

output
------

For drafting stages I prefer HTML output. Later we will cover how to manage Word Styles to customize the design of Word output documents.

You may experiment with Word output on your own.

Next tutorial: [run an R script from the Rmd script](tut-0605_rmd-run-r.md)

------------------------------------------------------------------------

[main page](../README.md)<br> [topics page](../README-by-topic.md)