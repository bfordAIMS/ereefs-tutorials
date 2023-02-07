# NOTE: *work in progress*

## User overview

This repository holds the source files for the AIMS Knowledge Systems eReefs tutorials hosted as [](bfordAIMS.github.io/ereefs-tutorials). 

Currently the site holds a single tutorial for plotting eReefs time series data in `R`. However, in time we hope to include a range of tutorials in both `R` and `python`. If you wish to see a tutorial on a specific topic you can add a request using the Github Issues feature, though please note that the development of subsequent tutorials is dependent on the time availability of AIMS staff.


# Developer overview

This is a static [Quarto website](https://quarto.org/docs/websites) hosted by Github Pages. 

Webpages can be edited and added via the Github repository. To do this we must clone the repository, make changes to the relevant Quarto (`.qmd`) documents, or add new Quarto documents to add new webpages, render to amended website on a local machine (using Quarto), and then push the changes to the repository.

> *Note:* This process can be changed by using Github Actions to render the Quarto website, though at present local rendering is sufficient. 

## File structure

The website source files are contained in the root directory and subfolders, excluding the following subfolders:

* `docs` contains the rendered website files - do not edit these file directly, they are updated automatically by Quarto upon rendering the website source files

* `_extensions` contains Quarto extensions which extend Quarto's functionality (e.g. we use the fontawesome extension to include icons in virtually any of the website's text)

* `.quarto` contains files used by Quarto behind the scenes - do not edit these files; knowledge of these files is not needed

### Website source files

* Individual webpages correspond to individual `.qmd` files; notably this includes:

  - `index.qmd` the homepage
  - `<file_name>.qmd` other webpages (note that these pages must be linked to, either directly or derivatively, from the home page or else will not be reachable)

* `_quarto.yml` is used to set global YAML settings (including theming and navigation)

* `style.css` is a global CSS style sheet applied to all webpages (sourced in the `.yml` file)

* Individual tutorials are contained within 

