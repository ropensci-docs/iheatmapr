# Convert Iheatmap to plotly spec

Function to convert `link{Iheatmap-class}` object to a plotly spec
either as a list or json

## Usage

``` r
to_plotly_list(p)

to_plotly_json(p)
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object to convert

## Value

Returns a JSON for a plotly spec for to_plotly_spec and as a list of
same plotly object for to_plotly_list.

## Examples

``` r

mat <- matrix(rnorm(24), nrow = 6)
hm_json <- iheatmap(mat) %>% to_plotly_json()
hm_list <- iheatmap(mat) %>% to_plotly_list()
```
