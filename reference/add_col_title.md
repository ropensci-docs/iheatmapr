# add_col_title

Add x axis title to plot

## Usage

``` r
# S4 method for class 'Iheatmap'
add_col_title(
  p,
  title,
  textangle = 0,
  font = get_layout(p)$font,
  side = c("bottom", "top"),
  size = 0.1,
  buffer = 0.01,
  xname = current_xaxis(p),
  yname = NULL
)
```

## Arguments

- p:

  iheatmap object

- title:

  title of axis

- textangle:

  angle of text

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

[`add_col_labels`](https://docs.ropensci.org/iheatmapr/reference/add_col_labels.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_row_title`](https://docs.ropensci.org/iheatmapr/reference/add_row_title.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm <- iheatmap(mat) %>% add_col_title("My x-axis")

# Print heatmap if interactive session 
if (interactive()) hm 
```
