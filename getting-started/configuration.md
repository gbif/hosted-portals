# How to configure your site

Many questions are best answered by the [Jekyll documentation](https://jekyllrb.com/), but questions that are specific to the theme or the widgets will be documented in this repository.

*The portals and search widgets is still under development, so this document will change as we progress.*

## Data scope

*Your data scope is unlikely to change very often, so we can help configuring it if you need help.*

You can configure your data scope in `/_includes/js/config.js`.

Below is an example of a site configured to only show fungi (i.e. taxonKey=5 in the GBIF backbone). Any predicate can be used. The format is defined in the [GBIF developer 

documentation](https://www.gbif.org/developer/occurrence#predicates)
```
var siteConfig = {
  rootPredicate: { type: 'equals', key: 'taxonKey', value: 5 }
};
```

## This documentation is a stub
A lot of documentation is still missing. This comes to mind:

* theme specific Jekyll variables, layouts etc.
* How to use the js components for dynamic counts
* widget styling
* how to overwrite css
* how to change widget language
* How to contribute translations of the widgets
* Essentially anything related to the widgets. E.g. How to customize table columns, add custom filters etc.
