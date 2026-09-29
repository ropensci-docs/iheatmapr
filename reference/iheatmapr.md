# iheatmapr

Interactive complex heatmaps in R

## Details

iheatmapr is a package for building complex, interactive heatmaps in R
that can be explored in interactive R sessions or incorporated into
rmarkdown documents, shiny applications, or standalone html files.

The package includes a modular system for building up complex heatmaps,
where subplots get iteratively added to the top/left/right/bottom of the
main heatmap(s). The
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md)
function provides a wrapper around many of the common modular
subcomponents to build fairly standard, moderately complex heatmap.

See the vignette for detailed instructions for how to use the package.

iheatmapr uses the plotly javascript library (<https://plotly.com/>) for
making the interactive figures and htmlwidgets
(http://www.htmlwidgets.org/) for rendering them in R.

## See also

[`main_heatmap`](https://docs.ropensci.org/iheatmapr/reference/main_heatmap.md),
[`iheatmap`](https://docs.ropensci.org/iheatmapr/reference/iheatmap.md),
[`Iheatmap-class`](https://docs.ropensci.org/iheatmapr/reference/Iheatmap-class.md)

## Author

Alicia Schep
