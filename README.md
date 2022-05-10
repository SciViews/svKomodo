# svKomodo

<!-- badges: start -->

[![R-CMD-check](https://github.com/SciViews/svKomodo/workflows/R-CMD-check/badge.svg)](https://github.com/SciViews/svKomodo/actions) [![Win Build Status](https://ci.appveyor.com/api/projects/status/github/SciViews/svKomodo?branch=master&svg=true)](https://ci.appveyor.com/project/phgrosjean/svKomodo) [![Coverage Status](https://img.shields.io/codecov/c/github/SciViews/svKomodo/master.svg)](https://codecov.io/github/SciViews/svKomodo?branch=master) [![CRAN status](https://www.r-pkg.org/badges/version/svKomodo)](https://cran.r-project.org/package=svKomodo) [![License](https://img.shields.io/badge/license-GPL-blue.svg)](https://www.gnu.org/licenses/gpl-2.0.html) [![Lifecycle: superseded](https://img.shields.io/badge/lifecycle-superseded.svg)](https://www.tidyverse.org/lifecycle/#superseded)

<!-- badges: end -->

R-side code to implement an R editor and IDE in Komodo IDE (<https://www.activestate.com/products/komodo-ide/>) with the SciViews-K extension.

**Note that this package is maintained minimally in order to keep code that may be useful in another context. However, RStudio and VScode with R extensions are the R editors/IDEs that you should use today. Komodo + SciViews-K/svKomodo aimed to develop a similar R IDE back in the 2000's/2010's, but its development was stopped in 2016 when RStudio gained its popularity.**

## Installation

You can install the released version of {svKomodo} from [CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("svKomodo")
```

You can also install the latest development version. Make sure you have the {remotes} R package installed:

``` r
install.packages("remotes")
```

Use `install_github()` to install the {svKomodo} package from GitHub (source from **master** branch will be recompiled on your machine):

``` r
remotes::install_github("SciViews/svKomodo")
```

R should install all required dependencies automatically, and then it should compile and install {svKomodo}.

## Usage

You can get further help about this package this way: Make the {svKomodo} package available in your R session:

``` r
library("svKomodo")
```

Get help about this package:

``` r
library(help = "svKomodo")
help("svKomodo-package")
```

For further instructions, please, refer to the help pages at <https://www.sciviews.org/svKomodo/>.

## Code of Conduct

Please note that the svKomodo project is released with a [Contributor Code of Conduct](https://contributor-covenant.org/version/2/0/CODE_OF_CONDUCT.html). By contributing to this project, you agree to abide by its terms.
