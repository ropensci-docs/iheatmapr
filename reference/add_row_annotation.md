# add_row_annotation

Adds annotation heatmaps for one or more qualitative or quantitative
annotations for each row of a main heatmap.

## Usage

``` r
# S4 method for class 'Iheatmap'
add_row_annotation(
  p,
  annotation,
  colors = NULL,
  side = c("right", "left"),
  size = 0.05,
  buffer = 0.015,
  inner_buffer = buffer/2,
  layout = list(),
  show_colorbar = TRUE
)
```

## Arguments

- p:

  `link{Iheatmap-class}` object

- annotation:

  data.frame or object that can be converted to data frame

- colors:

  list of color palettes, with one color per annotation column name

- side:

  side of plot on which to add row annotation

- size:

  relative size of each row annotation

- buffer:

  relative size of buffer between previous subplot and row annotation

- inner_buffer:

  relative size of buffer between each annotation

- layout:

  layout properties for new x axis

- show_colorbar:

  logical indicator to show or hide colorbar

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
`add_row_annotation`,
[`add_col_signal`](https://docs.ropensci.org/iheatmapr/reference/add_col_signal.md),
[`add_col_groups`](https://docs.ropensci.org/iheatmapr/reference/add_col_groups.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(24), nrow = 6)
annotation <- data.frame(gender = c(rep("M", 3),rep("F",3)),
                        age = c(20,34,27,19,23,30))
hm <- iheatmap(mat) %>% add_row_annotation(annotation)

# Print heatmap if interactive session 
if (interactive()) hm 
```
