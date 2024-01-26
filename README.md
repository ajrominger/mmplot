# mmplot

*mmplot: multimethod plotting*, pronounced "mmm mmm plot" like "mmm mmm that tastes good"

This is mostly an excersise in what would be an ideal object oriented and multiple-dispatch centered plotting package for R.  The features I would like are:

- don't have to read a 600+ page book about grammer to understand why I'm writing some code to make a plot
- don't have to memorize a bunch of random-sounding functions to make a plot
- I want to say `plot(object)` and have it make the appropriate plot for that object 
- the defaults (and I can't stress this enough) **SHOULD LOOK GOOD**
- there should be consistent sizing across devices
    - if I save to PDF the fonts should look the same as saaving to JGP
    - if I resize the plot, the sizes of plot elements should change proportionately
    - there should be no more of this bs that if I render a plot in an md doc that making the graphic device *smaller* leads to **bigger** font!!!
- the multiple dispatch for things like phylogenies, geospatial data, timeseries, expressions should be pretty simple, it might be more hard for a lot of the "core" graphics, e.g.,
    - how do you specify how a data.frame should be plotted? it shouldn't always be a scatter plot, maybe we barrow **a few** ideas from the gg world (but let's please not call them cryptic names like `aes`)
    - do you need to define new classes for scatterplot, boxplot, etc?
    - then we make the object like `x <- scatterplot(data, ...)` and the plot it `plot(x)`???
    - or do we do like `plot(<put data.frame here>, x = <col_name>, y = <col_name or function>, ...)`?
    - where `y` is optional and could be left out (in which case it guesses what plot you want), or it could be a column (make a scatter plot) or it could be a function (e.g. `hist` it makes a histogram)

