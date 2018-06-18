# MasterThemes

A tooling infrastructure for building color themes.

## Overview

A set of tooling for building color themes and producing settings for a wide array of products from
terminals, editors, IDE's, to nearly any theme-able application.

In short, one master theme (hence the name) allows output for dozens of applications.

## Inspiration

MasterThemes was heavily inspired by [Base16](http://chriskempson.com/projects/base16/), for more
details please read [Inspiration](inspiration.md).

## Documentation

MasterThemes is designed in a two-layered file mapping system. First, you have the master color
theme (master theme or just theme for short) which houses the mappings between identifiable themed
slots (like "constant" or "comment") and the desired style of that item. Second, you have
application templates that map any number of those identifiable themed slots to a particular
applications theme format and identifiers. Master themes are intended to be used across different
application templates, and application templates are intended to be able to consume any master
theme.

Finally, a builder is a tool that can be used to combine a theme or themes with a template or
templates to produce the necessary output that can then be used with the desired application(s).

Detailed (and versioned) documentation for these components can be found below:

-   [Themes Specification](theme-spec.md)
-   [Templates Specification](template-spec.md)
-   [Builder Guidelines](builder-guildines.md)

## The Themes

The full list of themes can be found here: [Themes](themes.md)

## The Templates

The full list of application templates can be found here: [Templates](templates.md)

## The Builders

The full list of builders can be found here: [Builders](builders.md)

## Scheme Repositories

TBD

## Builder Repositories

TBD

## Other tools for using MasterThemes

TBD

## License

MIT © 2018 [Brennan Fee](https://github.com/masterthemes)
