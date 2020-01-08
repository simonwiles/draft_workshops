# Data Wrangling with OpenRefine

[![OpenRefine](https://raw.githubusercontent.com/simonwiles/draft_workshops/OpenRefine/OpenRefine/OpenRefine.440x104.png)](https://cidr.stanford.edu)
[![Center for Interdisciplinary Digital Research @ Stanford](https://raw.githubusercontent.com/sul-cidr/Workshops/master/cidr-logo.no-text.240x140.png)](https://cidr.stanford.edu)

OpenRefine is a powerful free and open source tool for wrangling data: exploring it, cleaning it, manipulating it, and transforming it from one format into another.  In this hands-on workshop we will introduce OpenRefine’s features and cover some of the ways it can be used to tame unruly datasets.  You'll learn how to search, sort, filter, and facet your data, how to fix inconsistencies and errors, and how to create semi-automated workflows for producing clean and consistent datasets for your research.  Even if you don’t think of your research materials as data, OpenRefine can help you clean up and make sense of spreadsheets you’ve created, text you’ve scraped from websites, and other structured sources.


## Installing OpenRefine
Go to [https://openrefine.org/download.html](https://openrefine.org/download.html) and download the distribution appropriate for your operating system.

* If you're on Windows, extract the zip file and run `openrefine.exe`.
* Mac users, open the `.dmg` file, drag the OpenRefine icon to your Applications folder, and the double-click to run it.
* For Linux, extract the tarball and execute `./refine`.


### A Note on Versions
(In 3.3beta "A new menu for joining (concatenating) columns has been added" which looks cool, but there seems to be a bug in facet clustering, so I'm working with 3.2 for now.


## Opening and Creating Projects
* data formats
* configuring import in the preview

## Exploring Data: Sorting, Filtering, and Faceting
* Sorting
* Filtering
* Facets
    - Text/Numeric/Date facets
    - Can't get scatterplot facets to work yet
    - Facet by choice counts


## Manipulating Data: Cleaning, Modifying, and Augmenting

### Row-wise Manipulation
* Flagging and then faceting

### Editing Multiple Values at Once


### Operating on Facets
* editing facets (for clean up)
* clustering facets


### Other Columnar Operations
* case conversion
* trimming whitespace
* splitting into multiple columns


### Expressions
* Custom facets with expressions
* Regex
* Jython
* https://github.com/OpenRefine/OpenRefine/wiki/Recipes


### Clustering on multi-valued fields
* splitting and joining multi-valued cells


## Saving Projects and Exporting Data
* Saving, Editing, and Importing Projects
* Exporting Data
    - tabular export (C/TSV, Excel, HTML)
    - as SQL
    - templating for (e.g.) JSON output
* Pipe-lining for iterable and reproducible workflows
    - Undo/Redo and exporting operations
        + change lists can be applied to data using (e.g.?) Python bindings, which is pretty cool :)
* Permalinks


## Advanced Topics
* Data Reconciliation (using external authority)
* Plugins / Extensions

