# add_main_heatmap

Adds an additional main heatmap to an iheatmap object

## Usage

``` r
# S4 method for class 'IheatmapHorizontal,matrix'
add_main_heatmap(
  p,
  data,
  name = "Signal",
  x = default_x(data),
  colors = pick_continuous_colors(zmid, zmin, zmax, p),
  colorbar_position = get_colorbar_position(p),
  show_colorbar = TRUE,
  zmin = min(data, na.rm = TRUE),
  zmax = max(data, na.rm = TRUE),
  zmid = 0,
  col_order = NULL,
  x_categorical = NULL,
  side = c("right", "left"),
  size = 1,
  buffer = 0.04,
  text = signif(data, digits = 3),
  tooltip = setup_tooltip_options(),
  xname = NULL,
  pname = name,
  ...
)

# S4 method for class 'IheatmapVertical,matrix'
add_main_heatmap(
  p,
  data,
  name = "Signal",
  y = default_y(data),
  colors = pick_continuous_colors(zmid, zmin, zmax, p),
  colorbar_position = get_colorbar_position(p),
  show_colorbar = TRUE,
  zmin = min(data, na.rm = TRUE),
  zmax = max(data, na.rm = TRUE),
  zmid = 0,
  row_order = NULL,
  y_categorical = NULL,
  side = c("bottom", "top"),
  size = 1,
  buffer = 0.04,
  text = signif(data, digits = 3),
  tooltip = setup_tooltip_options(),
  yname = NULL,
  pname = name,
  ...
)
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- data:

  matrix

- name:

  name of colorbar, will determine if colorbar is shared with existing
  plot

- x:

  x axis labels (by default rownames of data); only used if orientation
  is horizontal

- colors:

  color palette name or vector of colors

- colorbar_position:

  colorbar placement

- show_colorbar:

  display the colorbar?

- zmin:

  minimum for colorscale

- zmax:

  maximum for colorscale

- zmid:

  midpoint for scale

- col_order:

  column ordering for this heatmap; only used if orientation is
  horizontal

- x_categorical:

  is x categorical? will guess if not provided

- side:

  which side of the current plot to add this heatmap?

- size:

  relative size of plot. size relative to first heatmap

- buffer:

  amount of space to leave empty before this plot, relative to size of
  first heatmap

- text:

  text of value to display for data

- tooltip:

  tooltip options, see
  [`setup_tooltip_options`](https://docs.ropensci.org/iheatmapr/reference/setup_tooltip_options.md)

- xname:

  internal name for x axis

- pname:

  internal name for plot

- ...:

  additional arguments (ignored)

- y:

  y axis labels (by default colnames of data); only used if orientation
  is vertical

- row_order:

  row ordering for this heatmap; only used if orientation is vertical

- y_categorical:

  is y categorical? will guess if not provided

- yname:

  internal name for y axis

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`main_heatmap`](https://docs.ropensci.org/iheatmapr/reference/main_heatmap.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4) 
mat2 <-  matrix(rnorm(24), ncol = 6, nrow = 4) 
hm <- iheatmap(mat) %>% add_main_heatmap(mat2)

# Print heatmap if interactive session 
if (interactive()) hm 
```
