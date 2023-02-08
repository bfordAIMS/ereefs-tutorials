---
title: "eReefs Tutorials (WORK IN PROGRESS)"
---

# User overview

This repository holds the source files for the AIMS Knowledge Systems eReefs tutorials. 

Currently the site holds a single tutorial for plotting eReefs time series data in `R`. However, in time we hope to include a range of tutorials in both `R` and `python`. If you wish to see a tutorial on a specific topic you can add a request using the Github Issues feature, though please note that the development of subsequent tutorials is dependent on the time availability of AIMS staff.


# Developer overview

This is a static [Quarto website](https://quarto.org/docs/websites) hosted by Github Pages. 

Webpages can be edited and added via the Github repository. To do this we must clone the repository, make changes to the relevant Quarto (`.qmd`) documents, or add new Quarto documents to add new webpages, render the amended website on a local machine (using Quarto), and then push the changes to the repository.

> *Note:* This process can be changed by using Github Actions to render the Quarto website, though at present local rendering is sufficient. 

## Rendering the website

### Local machine requirements

To successfully render the website you will need the following software installed.

*Required*:

* [Quarto](https://quarto.org/docs/get-started)
* [R](https://www.r-project.org/)
* [Python](https://wiki.python.org/moin/BeginnersGuide/Download)
* The R packages and Python modules used within the scripts you are trying to render.

*Recommended*:

* [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* An IDE such as [R Studio](https://posit.co/downloads/) or [Visual Studio Code](https://code.visualstudio.com/download) (with the R, Python, and Quarto extensions)

> If you get the error `ImportError: DLL load failed: The specified module could not be found.` when rendering a python tutorial try the solutions [here](https://stackoverflow.com/questions/20201868/importerror-dll-load-failed-the-specified-module-could-not-be-found). Downloading [Microsoft Visual C++](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170) worked for me.


### Rendering process

#### 1. Clone the git repository to your machine

From the command line: 

```
git clone <repo url>
```

#### 2. Make changes:

**Edit existing tutorials** by editing the corresponding `tutorials/<language>/<tutorial-name>/<tutorial_name>.qmd` file. 
  
**Create a new tutorial** by creating a new folder in the corresponding `tutorials/<language>` folder; name it with the tutorial name; and create a `<tutorial_name>.qmd` file within the folder

#### 3. Render:

##### Entire website
Edits to the YAML or CSS files require you to render the entire website to implement the changes. You can do this with from the command line with

```
quarto preview <path to "ereefs-tutorials" folder> --render all --no-browser --no-watch-inputs
```

or by using the respective IDE controls (`ctrl+shft+p > Quarto: Render Project` in VS Code).

##### Single page
Edits to a single `.qmd` file can be rendered from the command line with 

```
quarto preview <path to file> --no-browser --no-watch-inputs
``` 

or by using the respective IDE controls (`ctrl+shft+p > Quarto: Render` in VS Code).


## File structure

The website is contained in the home folder `ereefs-tutorials`. Within this folder we have the following folders and files

:file_folder: `tutorials` contains the tutorial source files

$\hspace{0.5cm}\hookrightarrow$ `r` and `python` sort the source files by language

$\hspace{1cm}\hookrightarrow$ `<tutorial-name>` folders contain the files associated with a specific tutorial


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

