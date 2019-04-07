tables
================

<img src="../resources/cm308-header.png" width="100%" /> <small> <br>
<i>Mom’s Table</i> by Sara Shuman is licensed under
<a href="https://creativecommons.org/licenses/by/2.0//">CC BY 2.0</a>
<br> </small>

Intructions are for `github_document` output specifically. Our default
printing function is `knitr::kable()`.

## multiway data table

## table of representative data

When data set is large

## code chunk output

## xtable

xtable creates an HTML or LaTeX table, not sure we can use it with
`github_document`

``` r
library("xtable")
## Load example dataset
data(tli)

## Demonstrate data.frame
df <- tli[1:20, ] %>% 
    as.data.frame()



formatted_tbl <- xtable(df) 
    
print(formatted_tbl, type = "html", row.names = FALSE)
```

<!-- html table generated in R 3.5.3 by xtable 1.8-3 package -->

<!-- Sun Apr 07 14:49:22 2019 -->

<table border="1">

<tr>

<th>

</th>

<th>

grade

</th>

<th>

sex

</th>

<th>

disadvg

</th>

<th>

ethnicty

</th>

<th>

tlimth

</th>

</tr>

<tr>

<td align="right">

1

</td>

<td align="right">

6

</td>

<td>

M

</td>

<td>

YES

</td>

<td>

HISPANIC

</td>

<td align="right">

43

</td>

</tr>

<tr>

<td align="right">

2

</td>

<td align="right">

7

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

BLACK

</td>

<td align="right">

88

</td>

</tr>

<tr>

<td align="right">

3

</td>

<td align="right">

5

</td>

<td>

F

</td>

<td>

YES

</td>

<td>

HISPANIC

</td>

<td align="right">

34

</td>

</tr>

<tr>

<td align="right">

4

</td>

<td align="right">

3

</td>

<td>

M

</td>

<td>

YES

</td>

<td>

HISPANIC

</td>

<td align="right">

65

</td>

</tr>

<tr>

<td align="right">

5

</td>

<td align="right">

8

</td>

<td>

M

</td>

<td>

YES

</td>

<td>

WHITE

</td>

<td align="right">

75

</td>

</tr>

<tr>

<td align="right">

6

</td>

<td align="right">

5

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

BLACK

</td>

<td align="right">

74

</td>

</tr>

<tr>

<td align="right">

7

</td>

<td align="right">

8

</td>

<td>

F

</td>

<td>

YES

</td>

<td>

HISPANIC

</td>

<td align="right">

72

</td>

</tr>

<tr>

<td align="right">

8

</td>

<td align="right">

4

</td>

<td>

M

</td>

<td>

YES

</td>

<td>

BLACK

</td>

<td align="right">

79

</td>

</tr>

<tr>

<td align="right">

9

</td>

<td align="right">

6

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

WHITE

</td>

<td align="right">

88

</td>

</tr>

<tr>

<td align="right">

10

</td>

<td align="right">

7

</td>

<td>

M

</td>

<td>

YES

</td>

<td>

HISPANIC

</td>

<td align="right">

87

</td>

</tr>

<tr>

<td align="right">

11

</td>

<td align="right">

3

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

WHITE

</td>

<td align="right">

79

</td>

</tr>

<tr>

<td align="right">

12

</td>

<td align="right">

6

</td>

<td>

F

</td>

<td>

NO

</td>

<td>

WHITE

</td>

<td align="right">

84

</td>

</tr>

<tr>

<td align="right">

13

</td>

<td align="right">

8

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

WHITE

</td>

<td align="right">

90

</td>

</tr>

<tr>

<td align="right">

14

</td>

<td align="right">

5

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

WHITE

</td>

<td align="right">

73

</td>

</tr>

<tr>

<td align="right">

15

</td>

<td align="right">

8

</td>

<td>

F

</td>

<td>

NO

</td>

<td>

WHITE

</td>

<td align="right">

72

</td>

</tr>

<tr>

<td align="right">

16

</td>

<td align="right">

6

</td>

<td>

F

</td>

<td>

NO

</td>

<td>

BLACK

</td>

<td align="right">

82

</td>

</tr>

<tr>

<td align="right">

17

</td>

<td align="right">

4

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

WHITE

</td>

<td align="right">

69

</td>

</tr>

<tr>

<td align="right">

18

</td>

<td align="right">

3

</td>

<td>

F

</td>

<td>

YES

</td>

<td>

HISPANIC

</td>

<td align="right">

17

</td>

</tr>

<tr>

<td align="right">

19

</td>

<td align="right">

3

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

HISPANIC

</td>

<td align="right">

37

</td>

</tr>

<tr>

<td align="right">

20

</td>

<td align="right">

5

</td>

<td>

M

</td>

<td>

NO

</td>

<td>

WHITE

</td>

<td align="right">

70

</td>

</tr>

</table>

``` r
# set pander table-layout options
library(pander)
panderOptions('table.alignment.default', function(df)
    ifelse(sapply(df, is.numeric), 'right', 'left'))
panderOptions('table.split.table', Inf)
panderOptions('big.mark', ",")
panderOptions('keep.trailing.zeros', TRUE)


pander(df)
```

| grade | sex | disadvg | ethnicty | tlimth |
| ----: | :-- | :------ | :------- | -----: |
|     6 | M   | YES     | HISPANIC |     43 |
|     7 | M   | NO      | BLACK    |     88 |
|     5 | F   | YES     | HISPANIC |     34 |
|     3 | M   | YES     | HISPANIC |     65 |
|     8 | M   | YES     | WHITE    |     75 |
|     5 | M   | NO      | BLACK    |     74 |
|     8 | F   | YES     | HISPANIC |     72 |
|     4 | M   | YES     | BLACK    |     79 |
|     6 | M   | NO      | WHITE    |     88 |
|     7 | M   | YES     | HISPANIC |     87 |
|     3 | M   | NO      | WHITE    |     79 |
|     6 | F   | NO      | WHITE    |     84 |
|     8 | M   | NO      | WHITE    |     90 |
|     5 | M   | NO      | WHITE    |     73 |
|     8 | F   | NO      | WHITE    |     72 |
|     6 | F   | NO      | BLACK    |     82 |
|     4 | M   | NO      | WHITE    |     69 |
|     3 | F   | YES     | HISPANIC |     17 |
|     3 | M   | NO      | HISPANIC |     37 |
|     5 | M   | NO      | WHITE    |     70 |

## cells with multiple entries

## cells with links

## references

<div id="refs">

<div id="ref-Wickham+Grolemund:2017">

Wickham H and Grolemund G (2017) *R for Data Science.* O’Reilly Media,
Inc., Sebastopol, CA <https://r4ds.had.co.nz/>

</div>

</div>

***
<a href="#top">&#9650; top of page</a>    
[&#9665; calendar](../README.md#calendar)    
[&#9665; index](../README.md#index)