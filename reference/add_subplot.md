# add_subplot

Adds an arbitrary subplot to iheatmap

## Usage

``` r
# S4 method for class 'Iheatmap'
add_subplot(
  p,
  ...,
  side = c("top", "bottom", "right", "left"),
  layout = list(),
  size = 1,
  buffer = 0.1,
  xname = if (side %in% c("top", "bottom")) current_xaxis(p) else NULL,
  yname = if (side %in% c("left", "right")) current_yaxis(p) else NULL,
  pname = "subplot"
)
```

## Arguments

- p:

  iheatmap object

- ...:

  arguments to pass to plotly trace, see plotly.js documentation at
  <https://plotly.com/javascript/reference/>

- side:

  which side of the current plot to add this heatmap? "right",
  "left","top", or "bottom"

- layout:

  axis layout parameters (list)

- size:

  relative size of plot. size relative to first heatmap

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

[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md)

## Author

Alicia Schep

## Examples

``` r
mat <- matrix(rnorm(24), ncol = 6)
hm <- iheatmap(mat) %>% add_subplot(x = 1:5, y=1:5, side = "top")

# Print heatmap if interactive session 
if (interactive()) hm 
```
