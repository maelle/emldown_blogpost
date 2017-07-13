-   [What's EML, exactly, and why can't a human read it?](#whats-eml-exactly-and-why-cant-a-human-read-it)
-   [What does `emldown` do with your EML?](#what-does-emldown-do-with-your-eml)
-   [How can you contribute?](#how-can-you-contribute)

We all know we should document our data... Nowadays it's better practice to write metadata for a dataset based on a standard metadata format than, say, write a Word codebook with no template. A well-established standard is the Ecological Metadata Language, EML. If you follow the standard properly, you're sure to have quite well documented your data which gives you a good feeling. Moreover, this will allow easier sharing of that dataset later.

That said, it's not always fun to write said standard metadata. Although there's a very good package for helping you create the EML, [rOpenSci's EML package](https://github.com/ropensci/eml), documenting the data can be quite tedious and before you share the data on a public repository enforcing EML, what's your prize? Good conscience isn't very tangible. In our unconf project, we created an immediate gratification for EML users: a package that transforms the non-human readable EML file into a pretty documentation website for any dataset!

(or use Andrew's speech instead? :thinking\_face:)

What's EML, exactly, and why can't a human read it?
===================================================

[EML](https://en.wikipedia.org/wiki/Ecological_Metadata_Language) is a metadata standard originally created for the ecological sciences. In practice it's a set of XML schema documents, telling you what you need to document (e.g. the dataset creator) and how (format of the XML). As mentioned previously, using the `EML` R package one can create and read EML, and this without needing to learn about XML thanks to helper functions and [extensive documentation](https://ropensci.github.io/EML/). Although its name contains the word *ecological*, one can use EML for documenting other datasets, e.g. one of our team members uses it for documenting epidemiological datasets, because nothing she'd like to document is missing from the standard, and because of the existence of the `EML` R package.

After creating an EML for your data, you get an XML document that's, well... not very human readable.

![raw eml](figures/screenshot_raw_xml.png)

(!!! function not working currently) In the `EML` package there's a function called `eml_view` relying on the [`listviewer` package](https://github.com/timelyportfolio/listviewer) to produce an interactive view of the XML in the Viewer pane of say, RStudio, which allows to check some things quickly but which is far from being an user-friendly representation of the metadata.

What does `emldown` do with your EML?
=====================================

After installing the package, currently from Github, you can apply it to your EML...

``` r
devtools::install_github("ropenscilabs/emldown")
library("emldown")
render_eml(path_to_my_eml)
```

and get something like this!

![emldown](figures/screenshot_emldown.png)

This format is much more likely to make you and your collaborators happy. Note how little effort you needed to invest into making it!

The resulting website is based on [Bootstrap](https://getbootstrap.com/) and has some interactive components:

![demo1](figures/emldown_demo1.gif)

Geographic information turns into a map, made using [leaflet](https://rstudio.github.io/leaflet/):

![demo2](figures/emldown_demo2.gif)

Right now, we are able to capture some of the most common parts of Ecological Metadata Language, including the Title, Abstract, Authors, Keywords, Coverage (where in space and time the samples were taken), the Data Tables and Units associated with these.

![demo3](figures/emldown_demo3.gif)

You can see a live example of a website created with `emldown` [here](http://aammd.info/emldown/test.html)

How can you contribute?
=======================

Use the package to transform the EML you have lying around on your PC into a pretty website... and if you find a bug while doing so, we'll be happy to tackle it! Report any issue or feature request [here](https://github.com/ropenscilabs/emldown/issues), or feel free to contribute with code.

We're very happy to have been able to create this working package in two days and we not so secretly hope that it will contribute to making writing good metadata more attractive and therefore more common.
