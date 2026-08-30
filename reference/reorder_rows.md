# reorder_rows

Reorder the rows of an
[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object

## Usage

``` r
# S4 method for class 'IheatmapHorizontal,integer'
reorder_rows(p, row_order)

# S4 method for class 'IheatmapVertical,integer'
reorder_rows(p, row_order, yname = current_yaxis(p))
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- row_order:

  integer vector

- yname:

  name of yaxis to reorder, only applicable if object is oriented
  vertically

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_row_clustering`](https://docs.ropensci.org/iheatmapr/reference/add_row_clustering.md),
[`reorder_cols`](https://docs.ropensci.org/iheatmapr/reference/reorder_cols.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
dend <- hclust(dist(mat))
hm <- iheatmap(mat) %>% reorder_rows(dend$order)

# Print heatmap if interactive session 
if (interactive()) hm 
```
