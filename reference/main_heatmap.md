# main_heatmap

Plots initial heatmap, creates Iheatmap object

## Usage

``` r
# S4 method for class 'matrix'
main_heatmap(
  data,
  name = "Signal",
  x = default_x(data),
  y = default_y(data),
  colors = pick_continuous_colors(zmid, zmin, zmax),
  colorbar_grid = setup_colorbar_grid(),
  colorbar_position = 1,
  zmid = 0,
  zmin = min(data, na.rm = TRUE),
  zmax = max(data, na.rm = TRUE),
  orientation = c("horizontal", "vertical"),
  x_categorical = NULL,
  y_categorical = NULL,
  row_order = seq_len(nrow(data)),
  col_order = seq_len(ncol(data)),
  text = signif(data, digits = 3),
  tooltip = setup_tooltip_options(),
  xname = "x",
  yname = "y",
  pname = name,
  source = "iheatmapr",
  show_colorbar = TRUE,
  layout = list()
)
```

## Arguments

- data:

  matrix

- name:

  name of colorbar

- x:

  x axis labels (by default rownames of data)

- y:

  y axis labels (by default colnames of data)

- colors:

  color palette or vector of colors

- colorbar_grid:

  colorbar grid parameters, should be result from
  [`setup_colorbar_grid`](https://docs.ropensci.org/iheatmapr/reference/setup_colorbar_grid.md)

- colorbar_position:

  colorbar placement, should be positive integer

- zmid:

  midpoint for colorscale

- zmin:

  minimum for colorscale

- zmax:

  maximum for colorscale

- orientation:

  should new main plots be added horizontally or vertically?

- x_categorical:

  is x categorical? will guess if not provided

- y_categorical:

  is y categorical? will guess if not provided

- row_order:

  row ordering for this heatmap– will be used for all subsequent
  elements sharing y axis

- col_order:

  column ordering for this heatmap– will be used for all subsequent
  elements sharing x axis

- text:

  text of value to display for data

- tooltip:

  tooltip options, see
  [`setup_tooltip_options`](https://docs.ropensci.org/iheatmapr/reference/setup_tooltip_options.md)

- xname:

  internal name for xaxis

- yname:

  internal name for yaxis

- pname:

  internal plot name

- source:

  source name for use with shiny

- show_colorbar:

  logical to indicate whether to show colorbar

- layout:

  list of layout attributes to pass to plotly, eg. list(font = list(size
  = 15))

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_iheatmap`](https://docs.ropensci.org/iheatmapr/reference/add_iheatmap.md),
[`to_widget`](https://docs.ropensci.org/iheatmapr/reference/to_widget.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm <- main_heatmap(mat) 

# Print heatmap if interactive session 
if (interactive()) hm 
```
