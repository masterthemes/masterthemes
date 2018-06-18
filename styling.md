# Styling Guideline

**Version 0.1 BETA**

## Overview

base30 is designed in a three-layered mapping system. First you have the color palette, than you
have a mapping scheme, together they comprise the "color theme". Then you use an application
template, which is shared across all color themes, to generate a file of settings that can be used
with the given application.

The first layer in a color theme is the color palette. The palette comprises the entire list of
colors the theme can express. While templates are free to map directly from to these colors, most
should use the second layer instead.

The second layer in a color provides purpose and context to the various colors. Re-using a color
across multiple purposes is not only likely but necessary. Modifiers, such as bold, italic, and
underline, are supported as well although not all applications may support them.

These two sets of configurations comprise the "color scheme" and when combined with an applications
template produces the theme for that application.

While this layering is indeed more complex for the theme designer than simply having color slots
labeled as "green" or base0B with those "green" things always mapping to "Strings, Inherited Class,
Markup Code, Diff Inserted", it instead provides maximal flexibility while keeping the templates and
tools as straightforward as possible. It also avoids us setting a different color in "green", like
say orange, just because we don't want to use a green but want yet another orange color and our
orange "slots" are already taken. In short, the burden and power are where they belong, with the
theme designer, so they can have the greatest amount of control.

The theme decides what Primary01 is and that Primary01 gets mapped to Booleans and Constants perhaps
(and possibly should show up in bold).This way templates can focus on just saying that the
"booleans" color gets placed here in the file.

## Highlights

In the color palette there are 6 colors for background highlights. They are most commonly beneficial
to show code coverage results (lines hit/missed), highlight the current line, show selected text,
etc.

For the best results, you should strive to pick shades that the default text color and all primary
and accent colors look readable when these highlight colors are used as the background. This is so
that any syntax highlighting used in code are still clearly readable when the lines are styled.

## The Color Palette (by codename)

The color slots are:

-   dark1
-   dark2
-   light1
-   light2
-   highlight-line
-   highlight-selection
-   highlight-error
-   highlight-warning
-   highlight-success
-   highlight-neutral
-   primary1
-   primary2
-   primary3
-   primary4
-   primary5
-   primary6
-   primary7
-   primary8
-   accent1
-   accent2
-   accent3
-   accent4
-   accent5
-   accent6
-   accent7
-   accent8
-   error
-   warning
-   success
-   neutral

### Note on primary/accent colors

In each group there are 8 slots. This gives the ability to have 2 each of red, green, blue, yellow,
cyan\teal, magenta\pink, orange\brown, and finally purple\violet. The number of slots was
specifically designed to support that array of color variation, however, given their generic naming
you are not bound to that. You could have 4 reds and skip yellows or have 16 blues, should you
desire. It is entirely in your hands.

## Context Mappings (by codename)

### Goal

The color of the context roster is to provide maximal consistency of a given color theme across
applications. From editor to editor, terminal to terminal, as long as the same feature-set is
supported you should see exactly the same end-result. Obviously, if one editor supports bold but
another doesn't differences would be unavoidable, but at least in that case the same color should
show up.

As an example, say you make primary2 the most beautiful green you have ever seen and map that to
"identifiers" and set it to be bold. Than as that entry is mapped into a template you should always
see that green in that context (and bold if the tool supports it) regardless of which template is
being used (as long as the template uses the "identifiers" key).

### Format Options

The supported format indicators are supported:

-   bold
-   italic
-   underline

These indicators can be combined for an entry.

### The Contexts

These contexts are supported:

-   background
-   text
-   current-line-highlight
-   selection-background
-   comments
-   TBD... many, many more to come

### Example Entries

Within the mapping YAML file an entry looks like so:

TBD
