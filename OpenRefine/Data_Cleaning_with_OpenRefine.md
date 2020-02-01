[![Center for Interdisciplinary Digital Research @ Stanford](https://raw.githubusercontent.com/sul-cidr/Workshops/master/cidr-logo.no-text.240x140.png)](https://cidr.stanford.edu)

# Data Wrangling with OpenRefine

[![OpenRefine](https://raw.githubusercontent.com/simonwiles/draft_workshops/OpenRefine/OpenRefine/OpenRefine.440x104.png)](https://cidr.stanford.edu)


**Instructor:** Simon Wiles (simon.wiles@stanford.edu)

<div markdown="1" class="instruction">
**Please SIGN-IN for this workshop at [cidr.link/openrefine-signin](https://cidr.link/openrefine-signin){target="_blank"}**
</div>

OpenRefine is a powerful free and open source tool for wrangling data: exploring it, cleaning it, manipulating it, and transforming it from one format into another.  In this hands-on workshop we will introduce OpenRefine’s features and cover some of the ways it can be used to tame unruly datasets.  You'll learn how to search, sort, filter, and facet your data, how to fix inconsistencies and errors, and how to create semi-automated workflows for producing clean and consistent datasets for your research.  Even if you don’t think of your research materials as data, OpenRefine can help you clean up and make sense of spreadsheets you’ve created, text you’ve scraped from websites, and other structured sources.

---

## §0 Installing OpenRefine

<div markdown="1" class="instruction">
Go to [the OpenRefine Download page](https://openrefine.org/download.html){target="_blank"} and download the distribution appropriate for your operating system.

* If you're on Windows, extract the zip file and run `openrefine.exe`.
* Mac users, open the `.dmg` file, drag the OpenRefine icon to your Applications folder, and the double-click to run it.
* For Linux, extract the tarball and execute `./refine`.
</div>

### A Note on Versions
At time of writing, version 3.3 of OpenRefine is in RC-phase, but for this workshop please make sure you download and install OpenRefine version 3.2.

---

## §1 About OpenRefine
* **Useful for Fairly Large Datasets**
OpenRefine works well with datasets up to around 100,000 records with the default configuration.  If your dataset is larger than that you can allocate more memory, but OpenRefine is not necessarily the best choice for *very* large amounts of data.
* **Operate on Rows and Columns as well as Cells**
The ability to edit, correct, and maniputate whole rows and columns in a single repeatable operation can make light work of tasks that would often otherwise require a programming or scripting language.
* **A Non-Destructive Environment**
When your data has is loaded into an OpenRefine project, a copy is made and the original source is left untouched.  Furthermore, every operation you perform is logged and your cumulative operation history can be rewound and replayed at any time.  This makes OpenRefine an ideal environment in which to experiment and try out different approaches to manipulating your data in a consequence-free way.  It also means that a record of all the operations you have performed is available at all times, such that this record can be exported and applied to similar datasets or new versions of the same dataset.
* **Clustering Algorithms**
OpenRefine includes an extensive suite of clustering alogrithms that can be used to semi-automatically reconcile messy and inconsistent data values.
* **Remote APIs and Reconcilliation**
Built-in support is available for fetching data from remote APIs to augment datasets, and third-party extensions exist that expand these options.  It is also possible to write custom extensions where appropriate.


## §2 Opening and Creating Projects
* Importing data from tabular and XML/JSON-based data sources is supposed, either from local files or pasted from the clipboard, or directly from a database or a URL.
* OpenRefine typically does a good job of introspecting the data and coming up with appropriate import settings, but you can alter the configuration if required as you create your project.
* When creating your project, choose a project name and add tags as desired to help you easily find your project in the future.

> Create a new project, importing data from the URL: https://cidr.link/openrefine-imdb
Check that the preview looks correct, then give the project an appropriate name and hit "Create Project".


## §3 A Tour of the OpenRefine UI
OpenRefine presents your data in a tabular form, similar to what you will be used to in a spreadsheet.  Some of the features to notice right away are:

* Record / Row count
* Record / Row selector
* Paging controls
* Column context menus
* The “All” column -- a star, a flag, and a number.
* Sidebar - Facet/Filter and Undo/Redo
* Permalinks

## §4 Exploring Data: Sorting, Filtering, and Faceting
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


## §5 Manipulating Data: Cleaning, Modifying, and Augmenting

> For this section, we'll use a different dataset.  Please create a new project and import the data from this URL: https://cidr.link/openrefine-safi

### Removing Rows
Sometimes our data is so messy that our first task is to drop some records that we don't want or need, or that are simply junk or otherwise unusuable.

* **Removing rows by criterion**
We might, for example, decide that we're not interesting in any records which have an *interview_date* before 2017.  To dispose of these records, we can filter them using a timeline facet, and remove them by using `All → Edit rows → Remove all matching rows`.
* **Flagging and then filtering**
If we need to manually remove rows in a way that can't be easily specified with a filter, one approach is to identify the rows we're interested by hand and flag them. We can then filter on the flag status and remove the offending rows in the same way.
* **Removing duplicates**
A common task is to identify and remove duplicate records in a data set.  If duplicate rows can be identified by a duplicate key of some kind, this becomes a straightforward task.  Sort the data according to the key in question, make sure to `Reorder rows permanently`, and then apply the `Edit cells → Blank down` operation.  The column can then be filtered on blanks as a proxy to select the duplicate records which can then be removed from the dataset.

### Cell-wise Transforms
OpenRefine offers a number of built-in data transformation functions that you can apply right way to solve common data-cleaning problems.

* Data-type conversion -- use the Undo/Redo list to see how many cells are affected, and sort on errors as appropriate.
* Case conversion
* Trimming whitespace -- see, e.g. *respondent_wall_type*
* etc.
* Transforms operate on the filtered set of records.

> **Exercise:** Remove *NULL* from the dataset by filtering and applying a `Common transformation`


### Expressions
These transformation functions are all applications of preset *expressions*, and OpenRefine exposes the power of its expression engine to us so that we can write our own to perform more sophisticated or specific operations in a similar column-wise manner.

* Transforming cells to allow custom faceting


* Regex, GREL and Jython
* see https://github.com/OpenRefine/OpenRefine/wiki/Recipes

### Other Columnar Operations
* **Splitting into multiple columns**
Try, for example, on a timestamp
* **Adding new columns by operating on existing ones**
* **Adding new columns by fetching from remote URLs**

## §6 Data Reconcilliation and Clustering
Data cleaning can be about fixing untidyness in the data, and reorganizing it, in the ways we've looked at above, but it can also involve reconciling data to homogenize labels, tags, and other values that refer to the same value in our analysis.

### Operating on Facets
* Editing facets (for clean up)
* Clustering facets

### Working with Multi-valued Cells
> For this section, we'll use a different dataset.  Please create a new project and import the data from this URL: https://cidr.link/openrefine-phm
For this dataset, please uncheck the option: `Use character " to enclose cells containing column separators.`

* splitting and joining multi-valued cells


## §7 Saving Projects and Exporting Data
* Saving, Editing, and Importing Projects
* Exporting Data
    - tabular export (C/TSV, Excel, HTML)
    - as SQL
    - templating for (e.g.) JSON output
* Pipe-lining for iterable and reproducible workflows
    - Undo/Redo and exporting operations
      change lists can be applied to data using (e.g.) Python bindings, which is pretty cool :)


