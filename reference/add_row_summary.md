# add_row_summary

Adds a line plot summarizing the values across rows

## Usage

``` r
# S4 method for class 'Iheatmap'
add_row_summary(
  p,
  groups = NULL,
  heatmap_name = NULL,
  colors = NULL,
  tracename = "Row Summary",
  showlegend = FALSE,
  side = c("right", "left"),
  layout = list(),
  size = 0.3,
  buffer = 0.02,
  xname = NULL,
  yname = current_yaxis(p),
  type = c("scatter", "bar"),
  summary_function = c("mean", "median", "sd", "var", "mad", "max", "min", "sum"),
  ...
)
```

## Arguments

- p:

  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- groups:

  vector of group labels, name of groups colorbar, or TRUE – see Details

- heatmap_name:

  name of a heatmap within the
  [`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
  object

- colors:

  vector of colors or RColorBrewer palette name

- tracename:

  name of trace

- showlegend:

  show legend?

- side:

  side of plot on which to add subplot

- layout:

  xaxis layout list

- size:

  relative size of subplot relative to main heatmap

- buffer:

  amount of space to leave empty before this plot, relative to size of
  first heatmap

- xname:

  internal name of xaxis

- yname:

  internal name of yaxis

- type:

  scatter or bar?

- summary_function:

  summary function to use, default is mean, options are mean, median,
  sd, var, mad, max, min, and sum

- ...:

  additional arguments to
  [`add_row_plot`](https://docs.ropensci.org/iheatmapr/reference/add_row_plot.md)
  or
  [`add_row_barplot`](https://docs.ropensci.org/iheatmapr/reference/add_row_barplot.md)

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## Details

If adding the row summary to a horizontally oriented heatmap, the
summary will be based on the right-most heatmap if side is "right" and
based on the left heatmap if side is "left" unless a "heatmap_name" is
specified. The heatmap_name should match the "pname" argument given to a
previously added heatmap.

The row summary is based on specific columns if a "groups" argument is
given. The groups argument can either be a vector of group assignments
for each row, the "pname" for an existing set of groups incorporated
into the plot using
[`add_col_groups`](https://docs.ropensci.org/iheatmapr/reference/add_col_groups.md),
[`add_col_annotation`](https://docs.ropensci.org/iheatmapr/reference/add_col_annotation.md),
[`add_col_clusters`](https://docs.ropensci.org/iheatmapr/reference/add_col_clusters.md),
or
[`add_col_clustering`](https://docs.ropensci.org/iheatmapr/reference/add_col_clustering.md).
If groups is set to TRUE, then the function will use an existing set of
column groups added to the plot.

## See also

[`add_col_summary`](https://docs.ropensci.org/iheatmapr/reference/add_col_summary.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_row_plot`](https://docs.ropensci.org/iheatmapr/reference/add_row_plot.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm1 <- iheatmap(mat) %>% add_row_summary()
hm2 <- iheatmap(mat) %>% add_row_summary(groups = c("A","A","B","B","B"))

# Print heatmap if interactive session 
if (interactive()) hm1
if (interactive()) hm2
```
