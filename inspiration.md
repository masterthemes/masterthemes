# Inspiration for MasterThemes

I am a big fan of [Base16](http://chriskempson.com/projects/base16/) and the excellent work by Chris
Kempson and the surrounding community of those projects. Many thanks go to him and the countless
others who helped him in that endeavor.

This system is heavily patterned after that organizational structure.

### So, why create a different system?

In short, greater color and style variety.

Base16 focuses most heavily on a legacy of limited color environments (like old terminals that
support 16 colors). This is the reason that a mere 16 colors/shades are allowed. On top of that
limitation, Chris chose a goal of having most templates be able to support a dark and light theme
within a single color palette. To support that goal, fully 8 of the "color slots" are traditionally
used for blacks/whites/grays for backgrounds and text. That is **HALF** of your choices of colors
gone merely to have two themes in one color set. You can see what I mean by the fact that in the
[Base16 Styling Guidelines](https://github.com/chriskempson/base16/blob/master/styling.md) two of
the colors have a comment of “(Not often used).” When you only have 16 colors to work with, any of
those selections not being used hurts quite a lot. Those two colors equate to 12.5% of your
available choices!

NOTE: I am fully aware that newer themes using Base16 forgo this light/dark reuse within a single
template, but it was part of the original design.

### Why are you dissing on Base16?

I'm seriously not, or at least not trying to. As I said, I am a huge fan and have used Base16 themes
for quite some time. However, I found that both in using and building them that the color selection
was just too limiting to provide the flexibility in the themes I wanted. It also has no support for
different features in the tools I was using (such as the use of bold or italics). On top of this, we
are largely in a new world were terminals are starting to support "True Color" and editors offer
even more significant and exciting ways to highlight and format colored syntax. More colors, mainly
colors that are highly visibly different, provide greater choice and flexibility.

### But in order for things to be mapped there must be some limitation? If not in color slots then where?

MasterThemes does limit the slots. It just offers a whole lot more slots than the 16 provided by
Base16. The slots provided by MasterThemes are identifiable by their intended use rather than some
arbitrary mapping. This mapping is stored in the theme, and a particular application template can
then use all the slots or - in the case of some older terminals - only the 16 slots it chooses. This
way with one master theme (hence the name MasterThemes) you can generate out high fidelity themes
for any number of applications. What a code "identifier" looks like in one application should look
the same in another (assuming similar support when font styles are used like bold).

While not supported yet, this also opens up the ability to theme more than just syntax color
elements. The theme slots in MasterThemes can be used to theme GUI elements like scrollbars,
buttons, menus, etc. As the project grows more slots and values will be added to allow application
templates more flexibility in what they can use for generation.

So, with MasterThemes the colors are unlimited, the slots are not.
