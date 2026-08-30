# S4 List Utils for Iheatmap classes

These are utility methods for list-like classes in the package.

## Usage

``` r
# S4 method for class 'IheatmapList'
length(x)

# S4 method for class 'IheatmapList'
as.list(x)

# S4 method for class 'IheatmapList'
x[i]

# S4 method for class 'IheatmapList'
x[i] <- value

# S4 method for class 'IheatmapList'
x[[i]]

# S4 method for class 'IheatmapList'
x[[i]] <- value

# S4 method for class 'IheatmapList'
x$name

# S4 method for class 'IheatmapList'
x$name <- value

# S4 method for class 'IheatmapList'
names(x)

# S4 method for class 'IheatmapList'
names(x) <- value

# S4 method for class 'IheatmapList'
lapply(X, FUN, ...)

# S4 method for class 'IheatmapList'
vapply(X, FUN, FUN.VALUE, ..., USE.NAMES = TRUE)
```

## Arguments

- x:

  input

- FUN:

  function to apply to each element of x

- ...:

  additional arguments

- FUN.VALUE:

  template for return value from FUN

- USE.NAMES:

  logical, use names?
