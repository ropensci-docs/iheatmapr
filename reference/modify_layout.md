# modify_layout

modify_layout

## Usage

``` r
# S4 method for class 'Iheatmap'
modify_layout(x, new_layout)
```

## Arguments

- x:

  Iheatmap

- new_layout:

  list of new layout parameter

## Value

modified Iheatmap object

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm <- main_heatmap(mat) %>% modify_layout(list(margin = list(b = 120))) 

# Print heatmap if interactive session 
if (interactive()) hm 
```
