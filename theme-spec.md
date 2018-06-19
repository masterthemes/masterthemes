# Theme Specification

Version 0.1 ALPHA

## Overview

Themes are housed within Git repositories. A single repository may contain multiple themes but all
theme files must exist at the root of the Git repo and contain a "json5" extension. It is
recommended, but not required, that the files begin with "masterthemes-" prefix. Everything after
the prefix will be considered the theme "slug" or identifier. Files without a prefix will use the
entire filename as the slug. The slug will be passed to templates but be transformed to all
lowercase with any spaces replaced with dashes.

As the extension indicates, we use the [JSON5](https://json5.org/) syntax for the theme format.
Every theme file will contain a "theme" key for the theme name and optional "author" and "theme-url"
keys for informational and attribution purposes.

It is recommended, but not required, to use a repository naming scheme of: [theme-name]-mastertheme
(with dashes as separators).

## Styles

Styles are the identifiable syntax elements that can contain the following information:

-   fgcolor - The foreground color, if background colors are not supported this will be the only
    color used.
-   bgcolor - The background color, if background colors are not supported this value is ignored.
-   format - An array of zero or more of the available text formats.

The formats support at present are: bold, italic, and underline.

An omitted value is interpreted the same as a blank or empty value. The effect is different per
item:

-   fgcolor - A blank foreground color automatically inherits the default text color.
-   bgcolor - A blank background color indicates "transparent" or, in effect, the default background
    color.
-   format - A blank format indicates a rendering with no text formatting applied.

### Colors

A color designation comes in two forms. A direct color or as an inherited identifier.

A direct color must be a hex string that begins with a # symbol. The syntax used is exactly the same
as CSS hex styles.

An inherited identifier must be a string and must indicate another identifier whose color is to be
used. Chains of inheritance can be formed but is discouraged for performance reasons. (A chain being
a color that points to another identifier that itself points to another identifier, and so on.)
Inherited identifiers are not allowed to cross color type, so foreground colors only inherit other
foreground colors.

Formats can not be inherited.

## Example

This is an abbreviated example.

```json5
{
    // Comments are supported, thanks to json5
    version: 0.1,  // Should match the version at the top of this documentation
    theme: "My Awesome Theme",
    author: "John Smith", // This value is optional
    theme-url: "https://github.com/jsmith/my-awesome-theme", // This value is optional
    styles: {
        background: {
            bgcolor: "#282936", // trailing commas are ok, again thanks to json5
            // omitted values are fine and interpreted as empty values
        },
        comment: {
            fgcolor: "#121212",
        },
        identifiers: {
            fgcolor: "comment", // inherits the color from comment above, so #121212
            format: [ bold, italic ],
        }
    },
}
```
