# Causal Inference: The Mixtape (*Fast Forward* ed.)


## Motivation

This is a hard fork of Scott Cunningham's 
[mixtape-learnr](https://github.com/scunning1975/mixtape_learnr) repo. The
original repo and the associated [textbook](https://www.amazon.com/dp/0300251688) 
are both outstanding pedagogical tools. So why the hard fork?

The short reason is that, upon reading through the material, I realised I would
write parts of the R code quite differently. (To be clear: There's no right or 
wrong way! Software pluralism FTW.) So, this forked version is simply to be 
consistent with the way I'd probably teach an econometrics course using Scott's
super book. Keeping with the mixtape theme, this "fast forward" edition tries to
be:

- **Lean:** My version of the code tries to be very concise (whilst hopefully 
maintaining readability). It also requires that users install and interact with 
as few libraries as possible. Despite the obvious benefits, the sheer number of 
available R libraries can be quite intimidating to new R users. My goal is to
encourage familiarity through consistency. 

- **Mean:** I also try to use best-in-class libraries/code with respect to
performance. While none of the estimations or simulations in Scott's book 
require particularly heavy lifting, the code herein should complete very 
quickly. More importantly, the performance benefits should carry over to cases 
where users adapt the code to their own, more computationally intensive 
research problems.

To achieve these dual goals, I lean heavily on three core libraries: 
[`data.table`](https://rdatatable.gitlab.io/data.table), 
[`fixest`](https://lrberge.github.io/fixest), and 
[`ggplot2`](https://ggplot2.tidyverse.org). 
While these three libraries get us 90% of the way towards replicating all of the 
code examples in the book, we occasionally have to grab a specialty library for 
some particular section (e.g. synthetic control). I also use the (new)
[`causaldata`](https://github.com/NickCH-K/causaldata) package to pull in the
datasets that Scott uses in his book. 

You can install all of the necessary libraries simply by opening up the repo's R 
project (click on the `mixtape_learnr-ff.Rproj` file) and running the following 
line in your R console:

```r
renv::restore(prompt = FALSE)
```

You are now good to go with respect to running of the R files in this repo.

The rest of this README is unchanged from the original.

## Using these files

First things first, you should fork this repository so you can make changes to the course and customize the files to your liking. To do this, you're in the right place. Click the fork button in the top right corner of this page.

![Fork this Repository](readme_files/fork.jpeg "Forking Repository")

There are three options for how to have students use these materials:

### 1. Run files using Learnr:

![Open file and click 'Run Document'](readme_files/rstudio_learnr_1.jpeg "Open .Rmd File and Click 'Run Document'")

![Run code](readme_files/rstudio_learnr_2.jpeg "Run Code")

### 2. Run files in RStudio:

You can also have students run R Markdown scripts directly from RStudio without using 'Run Document'. RStudio has great support for running code chunks and students would just have to hit the green play button to run each code chunk:

![Run code in RStudio](readme_files/rstudio_1.jpeg "Run Code in RStudio")

### 3. Run files in the web browser:

The last option allows you to launch the learnr html files directly into a url that students can open on their computer without even having to download R or RStudio. To do so, you will have to have an account with <https://www.shinyapps.io> (run by RStudio) which allows you to create a website and they will run the R Code on their servers. There is a free option that you can use for set up and trying it out, but if you plan on using this for the entire semester, you will probably want to upgrade to the Starter Plan which is \$10/month. This is because your students each will use up hours of compute time and someone needs to pay for the power.

Setting up Online Site:

For each .Rmd file you intend to use, you will have to publish a separate 'project' for this. After you set up you account and forking the repository, you will open your repository in RStudio ([more info on publishing here](https://rstudio.github.io/learnr/publishing.html)).

-   Open up the .Rmd file you wish to publish and click File -\> Publish.

-   Select the .Rmd file you wish to publish and the style.css file. Give this an appropriate title and click Publish.

![Publish to shinyapps.io](readme_files/publish.png "Publish to shinyapps.io")

-   This will take a few minutes and may require you to download some R packages, but afterwards it should open up the website in your web-browser. Copy this url.

-   Monitor your compute time usage on shinyapps.io to make sure you don't run out for the month when students are trying to use this!
