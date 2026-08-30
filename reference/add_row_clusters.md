# add_row_clusters

Add row groups and order rows based on groups

## Usage

``` r
# S4 method for class 'Iheatmap'
add_row_clusters(
  p,
  clusters,
  name = "Row<br>Clusters",
  reorder = TRUE,
  side = c("left", "right"),
  yname = current_yaxis(p),
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

- yname:

  name of yaxis

- ...:

  additional arguments to pass to
  [`add_row_groups`](https://docs.ropensci.org/iheatmapr/reference/add_row_groups.md)
  for creation of annotation heatmap indicating cluster membership

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## Details

This function is very similar to
[`add_row_groups`](https://docs.ropensci.org/iheatmapr/reference/add_row_groups.md);
the main difference is that with this function rows will get reordered
based on the groups.

## See also

[`add_row_clustering`](https://docs.ropensci.org/iheatmapr/reference/add_row_clustering.md),
[`add_col_clusters`](https://docs.ropensci.org/iheatmapr/reference/add_col_clusters.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)
clusters <- c("A","B","A","B")

hm <- iheatmap(mat) %>% add_row_clusters(clusters)

# Print heatmap if interactive session 
if (interactive()) hm
```
