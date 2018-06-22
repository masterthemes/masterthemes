# Template Specification

Version 0.1 ALPHA

## Overview

Templates are housed within Git repositories. Only a single target application can be referred to
within a template repository, but multiple templates are supported if the application requires
multiple files or if there are alternate versions that can be supported. Each repository must
contain a `config.json5` file at the root of the repository. This file drives the rest of the
process.

It is recommended, but not required, to use a repository naming scheme of:
masterthemes-template-[template-name] \(with dashes as separators).

For the template files themselves, the [Mustache](https://mustache.github.io/) template format
should be used.

## Config file

The config file contains information about the templates as well as what the application supports
for styling (like does it support bold).

### Sample `config.json5`

```json5
{
    version: 0.1, // This should match the version string at the top of this documentation.
    template: 'Sample Editor',
    author: 'John Smith', // optional
    templateUrl: 'https://github.com/johnsmith/masterthemes-sample-editor', // optional
    authorUrl: 'https://johnsmith.me', // optional
    applicationUrl: 'https://sampleeditor.org/', // optional, points to information on the themed application
    support: {
        backgroundColorsPerItem: true,
        bold: true,
        italic: true,
        underline: false,
    },
    files: [
        {
            template: 'templates/default.mustache',
            extension: '.yml',
        },
        {
            template: 'templates/256-alternate.mustache',
            extension: '-256.yml',
        },
    ],
}
```

## Template Variables

When a builder is used it will pass an object to the mustache templates. The structure of the object
is partially based off of the [Theme File](theme-spec.md). However, a number of changes will have
been made by the builder. Firstly, all identifier lookups will be resolved. Every color in the
Styles object will be a direct color.

Secondly, alternate versions of the colors will be included. This allows themes that only handle RGB
values to be used and so on.

Lastly, the formats will be broken out into explicit boolean indicators (is-bold, is-italic, etc.).
As well as given as a comma-separated list.

It should also be noted that no comments will flow through from the theme file so they can not be
used to pass information to the template.

So rather than looking like the input theme format, such as the following:

```json5
{
    version: 0.1,
    theme: 'My Awesome Theme',
    author: 'John Smith',
    themeUrl: 'https://github.com/jsmith/my-awesome-theme',
    authorUrl: '', // This is optional... a comment that won't get passed through to the template
    styles: {
        comment: {
            fgcolor: '#7cafc2',
        },
        identifiers: {
            fgcolor: 'comment',
            format: [bold, italic],
        },
    },
}
```

You will receive this:

```json5
{
    version: 0.1,
    theme: "My Awesome Theme",
    slug: "my-awesome-theme",
    author: "John Smith",
    themeUrl: "https://github.com/jsmith/my-awesome-theme",
    authorUrl: "",
    styles: {
        comment: {
            fgcolor: "#7cafc2"
            fgcolor-hex: "7cafc2"
            fgcolor-hex-r: "7c",
            fgcolor-hex-g: "af",
            fgcolor-hex-b: "c2",
            fgcolor-rgb-r: 124,
            fgcolor-rgb-g: 175,
            fgcolor-rgb-b: 194,
            fgcolor-dec-r: 0.87,
            fgcolor-dec-g: 0.50,
            fgcolor-dec-b: 0.21,
        },
        identifiers: {
            fgcolor: "#7cafc2"
            fgcolor-hex: "7cafc2"
            fgcolor-hex-r: "7c",
            fgcolor-hex-g: "af",
            fgcolor-hex-b: "c2",
            fgcolor-rgb-r: 124,
            fgcolor-rgb-g: 175,
            fgcolor-rgb-b: 194,
            fgcolor-dec-r: 0.87,
            fgcolor-dec-g: 0.50,
            fgcolor-dec-b: 0.21,
            format: [bold, italic],
            formatString: "bold,italic",
            is-bold: true,
            is-italic: true,
            is-underline: false,
        },
    },
}
```
