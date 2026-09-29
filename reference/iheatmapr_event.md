# Access iheatmapr user input event data in shiny

This function must be called within a reactive shiny context.

## Usage

``` r
iheatmapr_event(
  object,
  event = c("hover", "click", "relayout"),
  session = shiny::getDefaultReactiveDomain()
)
```

## Arguments

- object:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- event:

  The type of plotly event. Currently 'plotly_hover', 'plotly_click',
  'plotly_selected', and 'plotly_relayout' are supported.

- session:

  a shiny session object (the default should almost always be used).

## Examples

``` r
if (FALSE) { # \dontrun{
shiny::runApp(system.file("examples", "shiny_example", package = "iheatmapr"))
} # }
```
