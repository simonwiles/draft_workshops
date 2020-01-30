# Data Wrangling with OpenRefine

[![OpenRefine](https://raw.githubusercontent.com/simonwiles/draft_workshops/OpenRefine/OpenRefine/OpenRefine.440x104.png)](https://cidr.stanford.edu)
[![Center for Interdisciplinary Digital Research @ Stanford](https://raw.githubusercontent.com/sul-cidr/Workshops/master/cidr-logo.no-text.240x140.png)](https://cidr.stanford.edu)

**Instructor:** Simon Wiles (simon.wiles@stanford.edu)

OpenRefine is a powerful free and open source tool for wrangling data: exploring it, cleaning it, manipulating it, and transforming it from one format into another.  In this hands-on workshop we will introduce OpenRefine’s features and cover some of the ways it can be used to tame unruly datasets.  You'll learn how to search, sort, filter, and facet your data, how to fix inconsistencies and errors, and how to create semi-automated workflows for producing clean and consistent datasets for your research.  Even if you don’t think of your research materials as data, OpenRefine can help you clean up and make sense of spreadsheets you’ve created, text you’ve scraped from websites, and other structured sources.


## About OpenRefine
* **Useful for Fairly Large Datasets**
OpenRefine works well with datasets up to around 100,000 records with the default configuration.  If your dataset is larger than that you can allocate more memory, but OpenRefine is not necessarily the best choice for *very* large amounts of data.
* **Operate on Rows and Columns as well as Cells**
The ability to edit, correct, and maniputate whole rows and columns in a single repeatable operation can make light work of tasks that would often otherwise require a programming or scripting language.
* **A Non-Destructive Environment**
When your data has is loaded into an OpenRefine project, a copy is made and the original source is left untouched.  Furthermore, every operation you perform is logged and your cumulative operation history can be rewound and replayed at any time.  This makes OpenRefine an ideal environment in which to experiment and try out different approaches to manipulating your data in a consequence-free way.  It also means that a record of all the operations you have performed is available at all times, such that this record can be exported and applied to similar datasets or new versions of the same dataset.
* **Clustering Algorithms**
OpenRefine includes an extensive suite of clustering alogrithms that can be used to semi-automatically reconcile messy and inconsistent data values.
* **Remote APIs and Reconcilliation**
Plugins and extensions are available for fetching data from remote APIs to augment datasets.


## Installing OpenRefine
Go to [https://openrefine.org/download.html](https://openrefine.org/download.html) and download the distribution appropriate for your operating system.

* If you're on Windows, extract the zip file and run `openrefine.exe`.
* Mac users, open the `.dmg` file, drag the OpenRefine icon to your Applications folder, and the double-click to run it.
* For Linux, extract the tarball and execute `./refine`.


### A Note on Versions
Version 3.3 of OpenRefine is in RC-phase at the moment, but for this workshop please make sure you download and install OpenRefine version 3.2.


## Opening and Creating Projects
* Importing data from tabular and XML/JSON-based data sources is supposed, either from local files or pasted from the clipboard, or directly from a database or a URL.
* OpenRefine typically does a good job of introspecting the data and coming up with appropriate import settings, but you can alter the configuration if required as you create your project.
* When creating your project, choose a project name and add tags as desired to help you easily find your project in the future.

> Create a new project, using the URL https://
Check that the preview looks correct, then give the project an appropriate name and hit "Create Project".


## Exploring Data: Sorting, Filtering, and Faceting
The first thing that we might find OpenRefine useful for is exploring new datasets.

* **Sorting**
Sorting in OpenRefine works as expected.  Useful features include the ability to sort text in a case-sensitive or -insensitive way, and a convenient and simple method to sort empty values and processing errors to the top or bottom.
* **Filtering**
OpenRefine offers a straightforward text filter with options to control case-sensitivity and toggle regular expression parsing.  Despite its name, the text filter can be used on number and data columns to occassionally useful effect.
* **Facets**
Facets are where lot of the power of OpenRefine comes from, allowing sophisticated interrogation of data in real time.
    - Text/Numeric/Date facets
    Facets can be sorted by name or count, and toggled for use as inclusion or exclusion filters.
    - Scatter-plot facets are also available.
    - Custom facets allow for the specification of more sophisticated criteria and conditions


## Manipulating Data: Cleaning, Modifying, and Augmenting

> For this section, we'll use a different dataset.  Please create a new project and import the data from this URL: 

### Row-wise Manipulation
* Removing duplicates
* Flagging and then faceting

### Columnar Operations
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


### Operating on Facets
* editing facets (for clean up)
* clustering facets


## Saving Projects and Exporting Data
* Saving, Editing, and Importing Projects
* Exporting Data
    - tabular export (C/TSV, Excel, HTML)
    - as SQL
    - templating for (e.g.) JSON output
* Pipe-lining for iterable and reproducible workflows
    - Undo/Redo and exporting operations "Script Data Process"
        + change lists can be applied to data using (e.g.?) Python bindings, which is pretty cool :)
* Permalinks


## Advanced Topics
* Data Reconciliation (using external authority)
* Plugins / Extensions
* Python bindings

