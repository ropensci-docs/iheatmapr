# save_iheatmap

save an `link{Iheatmap-class}` object, either as standalone HTML or as
static pdf/png/jpeg

## Usage

``` r
# S4 method for class 'Iheatmap,character'
save_iheatmap(p, filename, ...)
```

## Arguments

- p:

  `link{Iheatmap-class}` object

- filename:

  name of file

- ...:

  additional arguments to
  [`saveWidget`](https://rdrr.io/pkg/htmlwidgets/man/saveWidget.html)
  for saving as html or
  [`webshot`](http://wch.github.io/webshot/reference/webshot.md) for
  saving as pdf/png/jpeg

## Details

Note that this function requires the webshot package. If deploying a
shiny app that calls this function in shinyapps.io, loading the webshot
library and calling
[`webshot::install_phantomjs()`](http://wch.github.io/webshot/reference/install_phantomjs.md)
is needed for the the save functionality to work.

## Author

Alicia Schep

## Examples

``` r
mat <- matrix(rnorm(24), nrow = 6)
hm <- iheatmap(mat)
if (FALSE) { # \dontrun{
save_iheatmap(hm, "example_iheatmap.png")
} # }
```
