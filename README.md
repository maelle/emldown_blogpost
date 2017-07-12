-   [What's EML, exactly, and why can't a human read it?](#whats-eml-exactly-and-why-cant-a-human-read-it)
-   [What does `emldown` do with your EML?](#what-does-emldown-do-with-your-eml)
-   [How can you contribute?](#how-can-you-contribute)

We all know we should document our data... Nowadays it's better practice to write metadata for a dataset based on a standard metadata format than, say, write a Word codebook with no template. A well-established standard is the Ecological Metadata Language, EML, which is a XML standard. If you follow the standard properly, you're sure to have quite well documented your data which gives you a good feeling, and will allow easier sharing of that dataset later.

That said, it's not always fun to write said standard metadata. Although there's a very good package for helping you create the EML, [rOpenSci's EML package](https://github.com/ropensci/eml), documenting the data can be quite tedious and before you share the data on a public repository enforcing EML, what's your prize? Good conscience isn't very tangible. In our unconf project, we created an immediate gratification for EML users: a package that transforms the non-human EML file into a pretty documentation website for any dataset!

(or use Andrew's speech instead? :thinking\_face:)

What's EML, exactly, and why can't a human read it?
===================================================

What does `emldown` do with your EML?
=====================================

-   add the gifs from `emldown` README

-   add a link to Andrew's online EML website.

How can you contribute?
=======================

Use the package to transform the EML you have lying around on your PC into a pretty website... and if you find a bug while doing so, we'll be happy to tackle it! Report any issue or feature request [here](https://github.com/ropenscilabs/emldown/issues).

We're very happy to have been able to create this working package in two days and not so secretly hope that it'll contribute to making writing metadata more attractive.
