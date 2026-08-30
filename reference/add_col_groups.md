# add_col_groups

Adds annotation to heatmap indicating what group every column of main
heatmap belongs to

## Usage

``` r
# S4 method for class 'Iheatmap'
add_col_groups(
  p,
  groups,
  name = "Column<br>Groups",
  title = "Groups",
  colors = pick_discrete_colors(groups, p),
  colorbar_position = get_colorbar_position(p),
  show_colorbar = TRUE,
  show_title = TRUE,
  side = c("top", "bottom"),
  layout = list(),
  size = 0.05,
  buffer = 0.015,
  tooltip = setup_tooltip_options(),
  xname = current_xaxis(p),
  yname = NULL,
  pname = name
)
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- groups:

  vector of group names

- name:

  name of colorbar

- title:

  name of x axis label

- colors:

  palette name or vector of colors

- colorbar_position:

  colorbar placement

- show_colorbar:

  show the colorbar?

- show_title:

  show title as axis label

- side:

  side of plot on which to groups annotation

- layout:

  list of layout parameters for x axis

- size:

  relative size of dendrogram (relative to the main heatmap)

- buffer:

  amount of space to leave empty before this plot, relative to size of
  first heatmap

- tooltip:

  tooltip options, see
  [`setup_tooltip_options`](https://docs.ropensci.org/iheatmapr/reference/setup_tooltip_options.md)

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

[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_row_groups`](https://docs.ropensci.org/iheatmapr/reference/add_row_groups.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)
col_groups <- c("A","A","B","D","B")
hm <- iheatmap(mat) %>% add_col_groups(col_groups, name = "My Groups")

# Print heatmap if interactive session 
if (interactive()) hm 
```
