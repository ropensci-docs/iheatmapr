# add_col_clusters

Add column groups and order columns based on groups

## Usage

``` r
# S4 method for class 'Iheatmap'
add_col_clusters(
  p,
  clusters,
  name = "Col<br>Clusters",
  reorder = TRUE,
  side = c("top", "bottom"),
  xname = current_xaxis(p),
  ...
)
```

## Arguments

- p:

  iheatmap object

- clusters:

  cluster assignments, should be vector of integers, characters, or
  factors

- name:

  name of colorbar indicating cluster membership

- reorder:

  reorder rows based on clusters? default is TRUE

- side:

  side of plot on which to add subplot

- xname:

  name of xaxis

- ...:

  additional arguments to pass to
  [`add_col_groups`](https://docs.ropensci.org/iheatmapr/reference/add_col_groups.md)
  for creation of annotation heatmap indicating cluster membership

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## Details

This function is very similar to
[`add_col_groups`](https://docs.ropensci.org/iheatmapr/reference/add_col_groups.md);
the main difference is that with this function column will get reordered
based on the groups.

## See also

[`add_row_clusters`](https://docs.ropensci.org/iheatmapr/reference/add_row_clusters.md),
[`add_col_clustering`](https://docs.ropensci.org/iheatmapr/reference/add_col_clustering.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)
clusters <- c("A","B","A","B","A")

hm <- iheatmap(mat) %>% add_col_clusters(clusters)

# Print heatmap if interactive session 
if (interactive()) hm 
```
