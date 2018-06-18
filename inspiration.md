# Inspiration for base30

I am a big fan of [Base16](http://chriskempson.com/projects/base16/) and the excellent work by Chris
Kempson and the surrounding community of those projects.

This system is heavily patterned after that organizational structure.

### So, why create a different system?

In short, greater color variety. Base16 focuses most heavily on a legacy of color limited
environments (like old terminals that support 16 colors). This is the reason that a mere 16
colors/shades are supported. On top of that limitation Chris chose a goal of having most templates
be able to support a dark and light theme within a single color palette. To support that goal, fully
8 of the "color slots" are traditionally used for blacks/whites/grays for backgrounds and text. That
is **HALF** of your choices of colors gone just to support two themes in one color set. You can see
what I mean by the fact that in the
[Base16 Styling Guidelines](https://github.com/chriskempson/base16/blob/master/styling.md) two of
the colors have a comment of “(Not often used)”. When you only have 16 colors to work with, any of
those selections not being used hurts quite a lot.

### Why are you dissing on Base16?

I'm seriously not, or at least not trying to. Like I said, I am a huge fan and have used Base16
themes for quite some time. However, I found that both in using and building them that the color
selection was just too limiting to provide the themes I wanted in the tools I was using. On top of
this, we are largely in a new world were terminals are starting to support "True Color" and editors
offer even greater and more interesting ways to highlight and format colored syntax. More colors,
particularly colors that are highly visibly different, provide greater choice and flexibility.

### But 30 is just 14 more colors than base16, sure nice, but that doesn't sound like that much difference?

Firstly, 14 extra colors are a **LOT** in the grand scheme of creating a color palette to choose
from. It's almost double!

Secondly, base30 designates the colors a bit more specifically and thus allows a slightly better
alignment with editors/tools when it comes to mapping colors to a purpose. Along with that base30
supports format designations as well such as italic, bold, etc. Not all themes may support such
constructs, but for those that do a single theme palette can support them.

Thirdly, in base30 themes are either dark or light… not both. So no need to place colors in specific
slots just so the template can generate both light and dark themes (which I understand isn't as
common now with Base16 themes, but still base30 reduces the white/black/gray space to just 5 color
slots, yet again increasing slots for more specific color choices).

Finally, base30 attempts to provide a smooth abstraction of the color uses from restricted 16-color
environments like some terminals all the way up to every single color and format type being used in
full-fledged IDE's and editors. In short, we're trying to put the theme designers in charge of
controlling exactly how their theme should be expressed, not just the colors that should be used but
the context as well.

### But, if more colors are better, why not just allow unlimited colors?

Well, conceptually it would be nice to build a color palette of an unlimited variety of colors.
However, the problem comes in when you try and build tooling to map those colors to the various
applications color themes. Each application supports different mechanisms to do so and so the input
of colors need to be slotted consistently in order to better reuse the palette.

In short, we are attempting to create expressive themes not just a list of colors.
