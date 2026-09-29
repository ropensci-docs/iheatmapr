# add_row_title

Add y axis title to plot

## Usage

``` r
# S4 method for class 'Iheatmap'
add_row_title(
  p,
  title,
  textangle = ifelse(side == "left", -90, 90),
  font = get_layout(p)$font,
  side = c("left", "right"),
  size = 0.1,
  buffer = 0.01,
  xname = NULL,
  yname = current_yaxis(p)
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

  internal name for xaxis

- yname:

  internal name for yaxis

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_col_title`](https://docs.ropensci.org/iheatmapr/reference/add_col_title.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_row_labels`](https://docs.ropensci.org/iheatmapr/reference/add_row_labels.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm <- iheatmap(mat) %>% add_row_title("Samples")

# Print heatmap if interactive session 
if (interactive()) hm 
```
