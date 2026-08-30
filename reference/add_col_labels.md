# add_col_labels

Add x axis labels to plot

## Usage

``` r
# S4 method for class 'Iheatmap'
add_col_labels(
  p,
  tickvals = NULL,
  ticktext = NULL,
  textangle = -90,
  font = get_layout(p)$font,
  side = c("bottom", "top"),
  size = 0.1,
  buffer = 0.005,
  xname = current_xaxis(p),
  yname = NULL
)
```

## Arguments

- p:

  `link{Iheatmap-class}` object

- tickvals:

  column indices at which to place axis tick labels

- ticktext:

  text for axis tick labels

- textangle:

  angle for ticktext

- font:

  list of plotly font attributes, see
  <https://plotly.com/javascript/reference/#layout-font>

- side:

  side of plot on which to add subplot

- size:

  relative size of subplot relative to main heatmap

- buffer:

  amount of space to leave empty before this plot, relative to size of
  first heatmap

- xname:

  name for xaxis

- yname:

  name for yaxis

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_row_title`](https://docs.ropensci.org/iheatmapr/reference/add_row_title.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
`add_col_labels`

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm1 <- iheatmap(mat) %>% add_col_labels()
hm2 <- iheatmap(mat) %>% add_col_labels(ticktext = letters[22:26])

# Print heatmap if interactive session 
if (interactive()) hm1
if (interactive()) hm2
```
