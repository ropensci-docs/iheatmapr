# add_iheatmap

add_iheatmap

## Usage

``` r
# S4 method for class 'IheatmapHorizontal,matrix'
add_iheatmap(
  p,
  data,
  x = default_x(data),
  cluster_cols = c("none", "hclust", "kmeans", "groups"),
  col_clusters = NULL,
  col_k = NULL,
  col_clust_dist = stats::dist,
  name = "Signal",
  scale = c("none", "rows", "cols"),
  scale_method = c("standardize", "center", "normalize"),
  colors = NULL,
  col_clusters_colors = NULL,
  col_clusters_name = "Col<br>Clusters",
  show_col_clusters_colorbar = TRUE,
  row_annotation = NULL,
  col_annotation = NULL,
  row_annotation_colors = NULL,
  col_annotation_colors = NULL,
  row_labels = NULL,
  col_labels = NULL,
  row_title = NULL,
  col_title = NULL,
  buffer = 0.2,
  ...
)

# S4 method for class 'IheatmapVertical,matrix'
add_iheatmap(
  p,
  data,
  y = default_y(data),
  cluster_rows = c("none", "hclust", "kmeans", "groups"),
  row_clusters = NULL,
  row_k = NULL,
  row_clust_dist = stats::dist,
  name = "Signal",
  scale = c("none", "rows", "cols"),
  scale_method = c("standardize", "center", "normalize"),
  colors = NULL,
  row_clusters_colors = NULL,
  row_clusters_name = "Col<br>Clusters",
  show_row_clusters_colorbar = TRUE,
  row_annotation = NULL,
  col_annotation = NULL,
  row_annotation_colors = NULL,
  col_annotation_colors = NULL,
  row_labels = NULL,
  col_labels = NULL,
  row_title = NULL,
  col_title = NULL,
  buffer = 0.2,
  ...
)
```

## Arguments

- p:

  iheatmap object

- data:

  matrix of values to be plotted as heatmap

- x:

  x xaxis labels, by default colnames of data

- cluster_cols:

  "none","hclust", or "k-means" for no clustering, hierarchical
  clustering, and k-means clustering of columnsrespectively

- col_clusters:

  vector of pre-determined column cluster assignment

- col_k:

  number of clusters for columns, needed if cluster_rows is kmeans or
  optional if hclust

- col_clust_dist:

  distance function to use for column clustering if hierarchical
  clustering

- name:

  Name for colorbar

- scale:

  scale matrix by rows, cols or none

- scale_method:

  what method to use for scaling, either standardize, center, normalize

- colors:

  name of RColorBrewer palette or vector of colors for main heatmap

- col_clusters_colors:

  colors for col clusters annotation heatmap

- col_clusters_name:

  name for col clusters colorbar

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

- buffer:

  amount of space to leave empty before this plot, relative to size of
  first heatmap

- ...:

  additional argument to add_iheatmap

- y:

  y axis labels, by default rownames of data

- cluster_rows:

  "none","hclust", or "k-means" for no clustering, hierarchical
  clustering, and k-means clustering of rows respectively

- row_clusters:

  vector of pre-determined row cluster assignment

- row_k:

  number of clusters for rows, needed if cluster_rows is kmeans or
  optional if hclust

- row_clust_dist:

  distance function to use for row clustering if hierarchical clustering

- row_clusters_colors:

  colors for row clusters annotation heatmap

- row_clusters_name:

  name for row clusters colorbar

- show_row_clusters_colorbar:

  show the colorbar for row clusters?

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

[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`main_heatmap`](https://docs.ropensci.org/iheatmapr/reference/main_heatmap.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(24), nrow = 6)
mat2 <- matrix(rnorm(24), nrow = 6)
annotation = data.frame(gender = c(rep("M", 3),rep("F",3)),
                        age = c(20,34,27,19,23,30))
hm <- iheatmap(mat, 
 cluster_rows = "hclust", 
 cluster_cols = "hclust", 
 col_k = 3) %>%
add_iheatmap(mat2, 
 cluster_cols = "hclust", 
 col_k = 3, 
 row_annotation = annotation)

# Print heatmap if interactive session 
if (interactive()) hm 
```
