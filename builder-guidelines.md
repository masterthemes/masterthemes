# Builder Guidelines

Version 0.1 ALPHA

## Overview

A MasterTheme builder is a tool that can produces output for applications that support theming. It
takes input themes and input application templates, combines them and produces the desired output.

Builders are versioned along with the MasterThemes specifications they support and generally target
only the major version. We use [semantic versioning](https://semver.org/) so any minor version
updates in the specifications should be backward compatible with builders that target the same major
version. All of the specifications for MasterThemes are versioned together to avoid conflicts or
gaps between them.

It is up to a builder if it chooses to support multiple versions - for backward compatibility sake.
However, at any given time the same major version of theme files should be used with the same major
version of application templates. So a particular builder could support both 1.x files as well as
2.x files but when processing only 1.x themes should be passed to 1.x templates. Generally, it would
be recommended not to support multiple versions due to the complexity it provides.

It is recommended, but not required, to use a repository naming scheme of:
masterthemes-builder-[language/platform] \(with dashes as separators).

## Bulk Processing or Options

Some builders may only support bulk processing, which is to say that every theme and every
application template will be processed. Others may allow you to pass a list of one or more of each.

## Workflow

The first thing a build needs to do is populate the list of theme and template repository sources.
These are housed in two Git repositories.

-   [Theme Sources](https://github.com/masterthemes/masterthemes-themes-source/)
-   [Template Sources](https://github.com/masterthemes/masterthemes-templates-source/)

Once those are cloned or updated, each contains a single JSON5 file called "list.json5". Each is an
array of objects with a theme or template name along with a Git repository URL. Bulk builders would
clone every one of the repos in each list, while other builders would only grab the desired
repositories requested by the user.

Once all repositories are collected\updated it can then go about the process of reading themes and
passing data to the application templates to produce the output.

## Theme Styles

It is up to the builder to resolve all theme colors that point to other identifiers and to calculate
the extra color inputs needed by templates. Please see the
[Template Specification](template-spec.md) for details.
