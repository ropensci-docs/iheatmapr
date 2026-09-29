# add_row_labels

Add y axis labels to plot

## Usage

``` r
# S4 method for class 'Iheatmap'
add_row_labels(
  p,
  tickvals = NULL,
  ticktext = NULL,
  textangle = 0,
  font = get_layout(p)$font,
  side = c("left", "right"),
  size = 0.1,
  buffer = 0.005,
  xname = NULL,
  yname = current_yaxis(p)
)
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- tickvals:

  row indices at which to place axis tick labels

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

  internal name for xaxis

- yname:

  internal name for yaxis

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_row_title`](https://docs.ropensci.org/iheatmapr/reference/add_row_title.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_col_labels`](https://docs.ropensci.org/iheatmapr/reference/add_col_labels.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm1 <- iheatmap(mat) %>% add_row_labels()
hm2 <- iheatmap(mat) %>% add_row_labels(ticktext = letters[23:26])


# Print heatmaps if interactive session 
if (interactive()) hm1
if (interactive()) hm2 
```
