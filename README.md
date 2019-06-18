# interpretable_ml-rsuite

## ebook built with rsuite. How is this different
This ebook was created with `bookdown`. It is different in the way it has been built, and can be rebuilt, even from the bare metal.

I have used `rsuite` to make it fully reproducible. This ebook is, in some way, difficult to match or keep all the dependencies. 
Unfortunately, not all good things last forever. After a package upgrade the ebook may stop building. These are all the packages required to build this ebook:

```
  logging,
  bookdown,
  ggplot2,
  mlbench,
  dplyr,
  tidyr,
  data.table,
  mlr,
  rpart,
  party,
  partykit,
  randomForest,
  gridExtra,
  grid,
  jpeg,
  caret,
  e1071,
  tm,
  svglite,
  mmpf,
  numDeriv,
  DT,
  xgboost,
  lubridate,
  pre,
  shiny,
  roxygen2,
  memoise, 
  gridExtra,
  OneR, 
  RWeka,
  sbrl,
  iml,
  jtools,
  mgcv,
  devtools,
  readr, 
  Cairo,
  viridis,
  interactions
```  

## How is it done

So, what I did is creating an isolated master project for the book, one where all the packages are spelled out in advance so the ebook can be rebuilt after: (i) an R re-installation, (ii) a new R version, or (iii) a full package upgrade. The book will be able to be regenerated to the CRAN snapshot at the time it was first built.

Because `rsuite` allows a supervising project on top of other projects or packages, you can control:

1. the date of the snapshot; 
1. the R version under you want the book to be built; 
1. the names of all the packages that satisfy the dependencies for the book to work; 
1. define a place for the source code of the package if the package is not in CRAN; 
1. a master project and a master package that takes care of reproducing the whole book, again and again, even after changing the operating system.
1. a master environment with its own scripts and configuration files on top of projects and packages.


## How to reproduce this ebook yourself
* Download and install the [RSuite](https://rsuite.io/) client. Available for Linux, Mac and Windows.
* Install the rsuite package with `rsuite install`
* Clone or download this repository.
* Change to this repo folder and install the dependencies on its own isolated reproducible environment. Use `rsuite proj depsinst`
* Build the project with `rsuite proj build`
* Go to the folder `/work/book`, or where the bookdown lives, and open the `.Rproj` project.
* Click on the RStudio **Build Book** button.
* Enjoy


## Publishing this book in Github pages
To publish this book in Github pages, push the folder `./work/book/public` as a branch `gh-pages` with this git command:

```
git subtree push --prefix work/book/public https://github.com/f0nzie/interopretable_ml-rsuite.git gh-pages
```

If you are building this in your own machine and own repository, change my username `f0nzie` by your own. This example assumes you are using `https` instead of `ssh`. Do not forget to activate `gh-pages` in *Settings, GitHub Pages*.


## References
* [Original repository](https://github.com/christophM/interpretable-ml-book)
* [Online ebook](https://christophm.github.io/interpretable-ml-book/)
* [Author's website](https://christophm.github.io/)
* [Bookdown website](https://bookdown.org/)
* [RSuite](https://rsuite.io/)
