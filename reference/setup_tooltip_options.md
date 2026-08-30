# Tooltip Options

This function setups tooltip options for heatmap components of iheatmapr
complex heatmaps.

## Usage

``` r
setup_tooltip_options(
  row = TRUE,
  col = TRUE,
  value = TRUE,
  prepend_row = "Row: ",
  prepend_col = "Col: ",
  prepend_value = "Value: "
)
```

## Arguments

- row:

  logical, include row name in tooltip?

- col:

  logical, include column name in tooltip?

- value:

  logical, include value in tooltip?

- prepend_row:

  text to prepend to row name

- prepend_col:

  text to prepend to column name

- prepend_value:

  text to prepend to value

## Value

a HeatmapTooltipOptions object which stores these options and can be
passed to 'tooltip' argument to main_heatmap and other functions.

## Examples

``` r

mat <- matrix(rnorm(20), ncol = 5, nrow = 4)  
hm1 <- main_heatmap(mat, 
   tooltip = setup_tooltip_options(row = FALSE, col = FALSE,
                                   prepend_value = "Value is ")) 

# Print heatmap if interactive session 
if (interactive()) hm1 
```
