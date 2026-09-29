# add_row_clustering

add_row_clustering

## Usage

``` r
# S4 method for class 'Iheatmap'
add_row_clustering(
  p,
  method = c("hclust", "kmeans", "groups"),
  name = "Row<br>Clusters",
  k = NULL,
  groups = NULL,
  clust_dist = stats::dist,
  colors = NULL,
  show_colorbar = TRUE,
  side = c("left", "right"),
  xname = NULL,
  yname = current_yaxis(p)
)
```

## Arguments

- p:

  iheatmap object

- method:

  "hclust" or "kmeans" for hierarchical or k-means clustering,
  respectively

- name:

  name of colorbar indicating cluster membership

- k:

  number of clusters for rows, needed if order is kmeans or optional if
  hclust

- groups:

  vector of group assignments

- clust_dist:

  distance function to use for clustering if hierarchical clustering

- colors:

  colors to use for annotation of grouping, can be RColorBrewer palette
  name or vector of colors

- show_colorbar:

  show the colorbar for the heatmap indicating cluster membership

- side:

  side of plot on which to add subplot

- xname:

  name of xaxis

- yname:

  name of yaxis

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_col_clustering`](https://docs.ropensci.org/iheatmapr/reference/add_col_clustering.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)
hm <- iheatmap(mat) %>% add_row_clustering(method = "hclust", k = 2)

# Print heatmap if interactive session 
if (interactive()) hm 
```
