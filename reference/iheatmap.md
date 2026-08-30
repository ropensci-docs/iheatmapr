# iheatmap

Make a farily standard interactive heatmap with optional clustering and
row and column annotations. For more flexibility and options, see the
[`main_heatmap`](https://docs.ropensci.org/iheatmapr/reference/main_heatmap.md)
function and other modular functions as described in vignette.

## Usage

``` r
# S4 method for class 'matrix'
iheatmap(
  data,
  x = default_x(data),
  y = default_y(data),
  cluster_rows = c("none", "hclust", "kmeans"),
  cluster_cols = c("none", "hclust", "kmeans"),
  row_clusters = NULL,
  col_clusters = NULL,
  row_k = NULL,
  col_k = NULL,
  row_clust_dist = stats::dist,
  col_clust_dist = stats::dist,
  name = "Signal",
  scale = c("none", "rows", "cols"),
  scale_method = c("standardize", "center", "normalize"),
  colors = NULL,
  col_clusters_colors = NULL,
  col_clusters_name = "Col<br>Clusters",
  row_clusters_colors = NULL,
  row_clusters_name = "Row<br>Clusters",
  show_row_clusters_colorbar = TRUE,
  show_col_clusters_colorbar = TRUE,
  row_annotation = NULL,
  col_annotation = NULL,
  row_annotation_colors = NULL,
  col_annotation_colors = NULL,
  row_labels = NULL,
  col_labels = NULL,
  row_title = NULL,
  col_title = NULL,
  colorbar_grid = setup_colorbar_grid(),
  layout = list(),
  source = "iheatmapr",
  ...
)
```

## Arguments

- data:

  matrix of values to be plotted as heatmap

- x:

  x xaxis labels, by default colnames of data

- y:

  y axis labels, by default rownames of data

- cluster_rows:

  "none","hclust", or "k-means" for no clustering, hierarchical
  clustering, and k-means clustering of rows respectively

- cluster_cols:

  "none","hclust", or "k-means" for no clustering, hierarchical
  clustering, and k-means clustering of columnsrespectively

- row_clusters:

  vector of pre-determined row cluster assignment

- col_clusters:

  vector of pre-determined column cluster assignment

- row_k:

  number of clusters for rows, needed if cluster_rows is kmeans or
  optional if hclust

- col_k:

  number of clusters for columns, needed if cluster_rows is kmeans or
  optional if hclust

- row_clust_dist:

  distance function to use for row clustering if hierarchical clustering

- col_clust_dist:

  distance function to use for column clustering if hierarchical
  clustering

- name:

  Name for colorbar

- scale:

  scale matrix by rows, cols or none

- scale_method:

  what method to use for scaling, either none, standardize, center,
  normalize

- colors:

  name of RColorBrewer palette or vector of colors for main heatmap

- col_clusters_colors:

  colors for col clusters annotation heatmap

- col_clusters_name:

  name for col clusters colorbar

- row_clusters_colors:

  colors for row clusters annotation heatmap

- row_clusters_name:

  name for row clusters colorbar

- show_row_clusters_colorbar:

  show the colorbar for row clusters?

- show_col_clusters_colorbar:

  show the colorbar for column clusters?

- row_annotation:

  row annotation data.frame

- col_annotation:

  column annotation data.frame

- row_annotation_colors:

  list of colors for row annotations heatmap

- col_annotation_colors:

  list of colors for col annotations heatmap

- row_labels:

  axis labels for y axis

- col_labels:

  axis labels for x axis

- row_title:

  x axis title

- col_title:

  y axis title

- colorbar_grid:

  colorbar grid parameters, should be result from
  [`setup_colorbar_grid`](https://docs.ropensci.org/iheatmapr/reference/setup_colorbar_grid.md)

- layout:

  list of layout attributes to pass to plotly, eg. list(font = list(size
  = 15))

- source:

  source name for use with shiny

- ...:

  additional argument to iheatmap

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## Details

By default, no scaling is done of rows or columns. This can be changed
by specifying the 'scale' argument. There are three options for scaling
methods. "standardize" subtracts the mean and divides by standard
deviation, "center" just subtracts the mean, and "normalize" divides by
the sum of the values. "normalize" should only be used for data that is
all positive! If alternative scaling is desired, the scaling should be
done prior to calling the iheatmap function.

## See also

`iheatmap`,
[`add_iheatmap`](https://docs.ropensci.org/iheatmapr/reference/add_iheatmap.md),
[`to_widget`](https://docs.ropensci.org/iheatmapr/reference/to_widget.md)

## Author

Alicia Schep

## Examples

``` r
mat <- matrix(rnorm(24), nrow = 6)
annotation = data.frame(gender = c(rep("M", 3),rep("F",3)),
 age = c(20,34,27,19,23,30))
hm <- iheatmap(mat, 
 cluster_rows = "hclust",
 cluster_cols = "kmeans", 
 col_k = 3, 
 row_annotation = annotation)

# Print heatmap if interactive session 
if (interactive()) hm 
```
