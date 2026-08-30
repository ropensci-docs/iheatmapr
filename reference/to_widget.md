# to_widget

Function to convert `link{Iheatmap-class}` object to widget object

## Usage

``` r
# S4 method for class 'Iheatmap'
to_widget(p)
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object to convert

## Value

htmlwidgets object

## See also

[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`main_heatmap`](https://docs.ropensci.org/iheatmapr/reference/main_heatmap.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(24), nrow = 6)
hm <- iheatmap(mat) %>% to_widget()
class(hm)
#> [1] "iheatmapr"  "htmlwidget"

# Print heatmap if interactive session 
if (interactive()) hm 
```
