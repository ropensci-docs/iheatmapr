# add_row_plot

Add a scatter or line plot with one point per row of the main heatmap

## Usage

``` r
# S4 method for class 'Iheatmap'
add_row_plot(
  p,
  x,
  ...,
  mode = c("lines+markers", "lines", "markers"),
  color = NULL,
  tracename = NA_character_,
  showlegend = !is.na(tracename),
  side = c("right", "left"),
  layout = list(),
  size = 0.2,
  buffer = 0.02,
  xname = NULL,
  yname = current_yaxis(p),
  pname = if (!is.na(tracename)) tracename else "row_plot"
)
```

## Arguments

- p:

  iheatmap object

- x:

  x axis values

- ...:

  additional arguments to add to plotly scatter trace, see
  <https://plotly.com/javascript/reference/#scatter>

- mode:

  mode of plot – one of "lines+markers","lines", or "markers"

- color:

  color of bars

- tracename:

  name of trace (for legend and hover)

- showlegend:

  show in legend?

- side:

  side of plot on which to add subplot

- layout:

  yaxis layout list

- size:

  relative size of subplot relative to main heatmap

- buffer:

  amount of space to leave empty before this plot, relative to size of
  first heatmap

- xname:

  internal name of xaxis

- yname:

  internal name of yaxis

- pname:

  internal name of plot

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_row_signal`](https://docs.ropensci.org/iheatmapr/reference/add_row_signal.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_row_barplot`](https://docs.ropensci.org/iheatmapr/reference/add_row_barplot.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm <- iheatmap(mat) %>% add_row_plot(x = 1:4, tracename = "Strength")

# Print heatmap if interactive session 
if (interactive()) hm 
```
