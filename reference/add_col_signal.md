# add_col_signal

Adds column signal to iheatmap object

## Usage

``` r
# S4 method for class 'Iheatmap'
add_col_signal(
  p,
  signal,
  name,
  title = name,
  yname = NULL,
  xname = current_xaxis(p),
  pname = name,
  colorbar_position = get_colorbar_position(p),
  colors = pick_continuous_colors(zmid, zmin, zmax, p = p),
  zmin = min(signal, na.rm = TRUE),
  zmax = max(signal, na.rm = TRUE),
  zmid = 0,
  side = c("top", "bottom"),
  size = 0.05,
  buffer = 0.015,
  text = signif(signal, digits = 3),
  tooltip = setup_tooltip_options(),
  show_colorbar = TRUE,
  show_title = TRUE,
  layout = list()
)
```

## Arguments

- p:

  iheatmap object

- signal:

  vector of signal

- name:

  name of colorbar

- title:

  label for y axis

- yname:

  internal name of yaxis

- xname:

  internal name of xaxis

- pname:

  internal name of plot

- colorbar_position:

  colorbar placement

- colors:

  palette or vector of colors to use

- zmin:

  minimum for colorscale

- zmax:

  maximum for colorscale

- zmid:

  midpoint for colorscale

- side:

  side of plot on which to add groups

- size:

  relative size of dendrogram (relative to the main heatmap)

- buffer:

  amount of space to leave empty before this plot, relative to size of
  first heatmap

- text:

  text of value to display for data

- tooltip:

  tooltip options, see
  [`setup_tooltip_options`](https://docs.ropensci.org/iheatmapr/reference/setup_tooltip_options.md)

- show_colorbar:

  show the colorbar?

- show_title:

  show title as axis label

- layout:

  y axis layout parameters to use

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_row_groups`](https://docs.ropensci.org/iheatmapr/reference/add_row_groups.md)

[`add_row_signal`](https://docs.ropensci.org/iheatmapr/reference/add_row_signal.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_col_annotation`](https://docs.ropensci.org/iheatmapr/reference/add_col_annotation.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm <- iheatmap(mat) %>% add_col_signal(signal = 1:5, name = "Strength")

# Print heatmap if interactive session 
if (interactive()) hm 
```
