# test_iheatmapr_event

test_iheatmapr_event

## Usage

``` r
test_iheatmapr_event(ihm, event = c("click", "hover", "relayout"))
```

## Arguments

- ihm:

  Iheatmap object

- event:

  name of event, either "click","hover", or "relayout"

## Value

shiny app

## Examples

``` r

if (FALSE) { # \dontrun{
  mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
  hm <- main_heatmap(mat) 
  test_iheatmapr_event(hm, "click")
} # }
```
