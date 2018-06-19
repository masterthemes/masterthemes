# MasterThemes

A tooling infrastructure for building color themes.

For the themes go here: [masterthemes.org](https://www.masterthemes.org/)

Version 0.1 ALPHA

## Overview

A set of tooling for building color themes and producing settings for a wide array of products from
terminals, editors, IDE's, to nearly any theme-able application.

In short, one master theme (hence the name) allows output for dozens of applications.

## Inspiration

MasterThemes was heavily inspired by [Base16](http://chriskempson.com/projects/base16/), for more
details, please read [Inspiration](inspiration.md).

## Documentation

MasterThemes is designed in a two-layered file mapping system. First, you have the master theme (or
just theme for short) which houses the mappings between identifiable themed slots (like constant,
identifier, or comment) and the desired style of that item (some blue color and bold, for instance).
Second, you have application templates that map any number of those identifiable themed slots to a
particular applications necessary format and identifiers. Master themes are intended to be used
across all application templates, and application templates are meant to be able to consume any
master theme.

Finally, a builder is a tool that can be used to combine a theme or themes with a template or
templates to produce the necessary output that can then be used with the desired application(s). A
builder is generally used by those of us writing themes and templates and are what produce the final
output.

Detailed (and versioned) documentation for these components can be found below:

-   [Themes Specification](theme-spec.md)
-   [Templates Specification](template-spec.md)
-   [Builder Guidelines](builder-guidelines.md)

## The Theme Repositories

The full list of theme repositories can be found here:
[Theme Repositories](https://www.masterthemes.org/theme-repositories.html/)

## The Template Repositories

The full list of application template repositories can be found here:
[Template Repositories](https://www.masterthemes.org/template-repositories.html/)

## The Builders

TBD

## Other tools for using MasterThemes

TBD

## License

MIT © 2018 [Brennan Fee](https://github.com/masterthemes)
