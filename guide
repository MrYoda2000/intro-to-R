# Introduction to R - Guide
## How to install R (Windows)
  1. Go to https://mirror.rcg.sfu.ca/mirror/CRAN/
  2.Click on “Download R for Windows”
  3. Click on “base”
  4. Click on “Download R 4.1.0 for Windows”

## How to install R (Mac)
  1. Go to https://mirror.rcg.sfu.ca/mirror/CRAN/
  2. Click on “Download R for (Mac) OS X”
  3. Check what processor you have by clicking the Apple logo and "About This Mac"
    a. Do you have an Intel chip? Click on “R-4.1.0.pkg”
    b. Do you have an M1 or other? Download from here https://www.rstudio.com/products/rstudio/download/preview/
  
## How to install R Studio
R is just the programming language. R studio is a program which makes it easier to use R. Think of it as our workspace for R.
  1. Go to https://rstudio.com/products/rstudio/download/#download
  2. Download RStudio for your system (Windows/Mac)
  
## Installing packages
Packages are like mods for R. They are a collection of functions to make your life easier.
For example, print() is a function.
  1. To install a package, on your console, type
     ```
     install.packages("package_name")
     ```
  
  2. We want to install “tidyverse”, so we’ll type
    install.packages("tidyverse")
3. Once we have our package installed, we need to activate it on our current session
    library(tidyverse)
    
Working with data in R
Let’s check that we did the above steps correctly. We’ll plot our first graph in R!
We already have a few pre-downloaded datasets so let’s work with that first (mpg: Fuel economy dataset)
1. Let’s call the function ggplot() to make our graphic.
  ggplot(mpg, aes(displ, hwy, colour = class)) + geom_point()

Importing data with R
Most of the time, we won’t have our data pre-loaded into our workspace. So, we’ll have to tell R where to find our data.
1. First, let’s download some example data. We’ll be working with “Cereal.csv” . It’s a univariate dataset with the weights of cereal boxes
2. Now let’s change our working directory (this tells R where to find our data)
3. Always remember to annotate your work! We do this by commenting with #
4. We want to import our csv and assign that data to a variable
    my_data <- read.csv("Cereal.csv")
  
Visualizing our imported data
We’re going to be creating a histogram of our cereal boxes. There are two ways to visualize we can do this. We can use basic R, or we can use our tidyverse (ggplot2) package.
I prefer using tidyverse because it’s more ✨aesthetic Method 1: Basic R
1. Super simple, we just use the following function
hist(my_data$Weight)
The dollar sign is just telling R to look at the “Weight”
column
2. We can change the title and a few other things
✨
    hist(my_data$Weight,
main="Histogram for Cereal Weight", xlab="Weight",
border="darkblue", col="lightblue",
las=1,
breaks=8)

With the above code, we are changing: our title,
the x-axis label, the colour of the bins and the border, y-axis label, and the number of bins.
3. We can change our graph to represent probability density instead (distribution). We just have to add one line of code inside our histogram function.
prob=TRUE
So, it should look like this now
  hist(my_data$Weight,
main="Histogram for Cereal Weight", xlab="Weight",
border="darkblue", col="lightblue",
las=1,
breaks=8,
prob=TRUE)
4. We can also add a density curve so we can actually see our distribution.
lines(density(my_data$Weight)) This should go outside the histogram function.
 
