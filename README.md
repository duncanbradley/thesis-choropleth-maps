# Chapter 5: Choropleth Maps Can Convey Absolute Magnitude Through the Range of the Accompanying Color Legend

* Data are in the `data` folder (this also contains the script for anonymising original data files)
* Analysis code is in the `ChoroplethMagnitude.qmd` (quarto) file

## Instructions for Using Docker To Generate the Manuscript Within a Fully-Reproducible Environment

This repository provides resources for re-creating the computational environment (R version, package versions) used for all data wrangling, data visualization, statistical modelling, and reporting. This will generate a fully interactive RStudio session, which will be running from a Docker container.

1. Download [Docker Desktop](https://www.docker.com) and launch it
2. Clone this repository to your local machine
3. Use the command line to navigate to the repository
4. Type `docker build -t thesis-choropleth-maps .` (where `thesis-choropleth-maps` is the repository name). This builds the Docker image.
5. Type `docker run --rm -p 8787:8787 -e PASSWORD=password thesis-choropleth-maps` to launch the Docker container.
6. In your browser's address bar, type `localhost:8787`
7. Enter `rstudio` as the username and `password` as the password. 
8. Open `ChoroplethMagnitude.qmd` and press Render to generate `ChoroplethMagnitude.pdf`

Note: Computationally intensive statistical models have been saved in `ChoroplethMagnitude_cache`. To speed-up rendering, these cached models are loaded instead of executing the code that generated them. To generate models from scratch, change the `eval_models` parameter in line 9 to `true`.

In case of a Sementation Fault error, add the following code to the script and run rmarkdown::render("ChoroplethMagnitude.qmd", output_file = "ChoroplethMagnitude.pdf")

knitr::opts_chunk$set(
  echo = FALSE, include = FALSE, warning = FALSE, message = FALSE
)
