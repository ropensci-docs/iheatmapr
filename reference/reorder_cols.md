# reorder_cols

Reorder the columns of an
[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object

## Usage

``` r
# S4 method for class 'IheatmapHorizontal,integer'
reorder_cols(p, col_order, xname = current_xaxis(p))

# S4 method for class 'IheatmapVertical,integer'
reorder_cols(p, col_order)
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- col_order:

  integer vector

- xname:

  name of xaxis to reorder, only applicable if object is oriented
  horizontally

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_row_clustering`](https://docs.ropensci.org/iheatmapr/reference/add_row_clustering.md),
`reorder_cols`

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
dend <- hclust(dist(t(mat)))
hm <- iheatmap(mat) %>% reorder_cols(dend$order)

# Print heatmap if interactive session 
if (interactive()) hm 
```
