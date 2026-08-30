# add_col_dendro

Adds column dendrogram to iheatmap object

## Usage

``` r
# S4 method for class 'Iheatmap,hclust'
add_col_dendro(
  p,
  dendro,
  reorder = TRUE,
  side = c("top", "bottom"),
  size = 0.15,
  buffer = 0.005,
  xname = current_xaxis(p),
  yname = NULL,
  sname = "col_dendro"
)
```

## Arguments

- p:

  iheatmap object

- dendro:

  hclust object

- reorder:

  reorder rows based on dendrogram order?

- side:

  side of plot on which to add dendro

- size:

  relative size of dendrogram (relative to the main heatmap)

- buffer:

  amount of space to leave empty before this plot, relative to size of
  first heatmap

- xname:

  internal name of xaxis

- yname:

  internal name of yaxis

- sname:

  internal name of shape

## Value

[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)
object, which can be printed to generate an interactive graphic

## See also

[`add_col_clustering`](https://docs.ropensci.org/iheatmapr/reference/add_col_clustering.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`add_row_dendro`](https://docs.ropensci.org/iheatmapr/reference/add_row_dendro.md)

## Author

Alicia Schep

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
dend <- hclust(dist(t(mat)))
hm <- iheatmap(mat) %>% add_col_dendro(dend)

# Print heatmap if interactive session 
if (interactive()) hm 
```
