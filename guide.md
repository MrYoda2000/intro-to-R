# Introduction to R - Guide
## How to install R (Windows)
1. Go to https://mirror.rcg.sfu.ca/mirror/CRAN/
2. Click on “Download R for Windows”
3. Click on “base”
4. Click on “Download R 4.1.0 for Windows”


## How to install R (Mac)
1. Go to https://mirror.rcg.sfu.ca/mirror/CRAN/
2. Click on “Download R for (Mac) OS X”
3. Check what processor you have by clicking the Apple logo and "About This Mac"

    a. Do you have an Intel chip? Click on “R-4.1.0.pkg”
    b. Do you have an M1 or other? Download from here https://www.rstudio.com/products/rstudio/download/preview/
    > This is a temporary solution for Mac's with the M1 chip. In the future you should download normally by clicking "R-4.1.0-arm64.pkg"
  
 
## How to install R Studio
R is just the programming language. R studio is a program which makes it easier to use R. Think of it as our workspace for R.
1. Go to https://rstudio.com/products/rstudio/download/#download
2. Download RStudio for your system (Windows/Mac)

## Installing packages
Packages are like mods for R. They are a collection of functions to make your life easier.
For example, ```print()``` is a function.

1. To install a package, type this in your console
    ```r
    install.packages("package_name")
    ```

2. We want to install “ggplot2”, so we’ll type
    ```r
    install.packages("ggplot2")
    ```
  > Normally, we'd want to install the package tidyverse, which includes gglplot2. But, there was a recent update in R and apparently it's incompatible for now.

3. Once we have our package installed, we need to activate it on our current session. Type this in your script
    ```r
    library(ggplot2)
    ```
    
## Working with data in R
Let’s check that we did the above steps correctly. We’ll plot our first graph in R!
We already have a few pre-downloaded datasets so let’s work with one of those first.
We'll be using "mpg", a dataset on fuel economy.
1. Let’s call the function ggplot() to make our graph.
    ```r
    ggplot(mpg, aes(displ, hwy, colour=class)) +
        geom_point()
    ```

## Importing data with R
Most of the time, we won’t have our data pre-loaded into our workspace. So, we’ll have to tell R where to find our data.
1. First, let’s download some example data. We’ll be working with “Cereal.csv” . (It’s a univariate dataset with the weights of cereal boxes)
2. Now, we need to tell R where to find our data. Of course, we need to know where our data is first before we can give R directions. So just remember where in your computer you downloaded "Cereal.csv" (If you moved the file around just find that folder)
3. Once you know where your data is in your computer, we change our working directory to that folder. For example, I have my data in a folder called "Data Folder" in my Desktop, so I type
    ```r
    setwd("~/Desktop/Data Folder")
    ```
4. Always remember to annotate your work! We do this by commenting with ```#``` So, we can improve our above code by commenting
    ```r
    # Changing working directory
    setwd("~/Desktop/Data Folder")
    ```
5. We want to import our csv and assign that data to a variable. We do this by using an arrow symbol ```<-``` on our variable (this is actually called an assignment operator) For this example, I'll be naming my variable ```my_data``` You can name your variable whatever you want, just make sure you are consistent for the rest of the exercise.
    ```r
    my_data <- read.csv("Cereal.csv")
    ```
  
## Visualizing our imported data
We’re going to be creating a histogram of our cereal boxes. There are two ways we can do this. We can use basic R, or we can use our tidyverse (ggplot2) package.
I prefer using tidyverse because it’s more ✨aesthetic✨ and allows for better data manipulation. For this exercise, I'll just be covering the basic R method.

### Method 1: Basic R
1. Super simple, we just use the following function
    ```r
    hist(my_data$Weight)
    ```
    > The dollar sign is just telling R to look at the “Weight” column
2. We can change the title and a few other things
    ```r
    hist(my_data$Weight,
        main="Histogram for Cereal Weight",
        xlab="Weight",
        border="darkblue",
        col="lightblue",
        las=1,
        breaks=8)
    ```
    With the code above, we are changing:
    * Our title
    * The x-axis label
    * The colour of the bins and the colour of the border
    * The rotation of y-axis label
    * The number of bins
3. We can change our graph to represent probability density (distribution) instead of frequency. We just have to add one line of code ```prob=TRUE``` inside our histogram function.
    So, it should look like this now
    ```r
    hist(my_data$Weight,
        main="Histogram for Cereal Weight",
        xlab="Weight",
        border="darkblue",
        col="lightblue",
        las=1,
        breaks=8,
        prob=TRUE)
    ```
4. We can also add a density curve so we can actually see our distribution.
    ```r
    lines(density(my_data$Weight))
    ```
    This should go outside the histogram function.

### Method 2: ggplot2
I encourage you to try it on your own!
To get you started you'll be using the ```ggplot()``` function. Just like we did with our very first exercise using the mpg dataset.

## That's it! Pat yourself in the back, you deserve it  :)
