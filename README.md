# Exploring Dialog Element

Implementing several approaches for the use of the <dialog> html
element, the goal was to get familiar with the element and it's api, as
well as explore possible options for no-js options for using it.

Overall the element is reasonable, and give a nicer, semantic tag for
a modal instead of a `<div aria_role="dialog"></div>`.

Positioning is tedious, based on margin sizes.
Animation is fine for displaying the modal, however it falls short on
closing the modal, as the browser is only concerned with the display
property and nothing else.

Without Javascript, you can achieve some modal-like functionality using
:target, :not, :has selectors, but I would not rely heavily on these for
complex operations. You could also use checkbox inputs and labels to
trigger the display for more stable control and without mangling the
browser history.

If building with progressive enhancement, the places I can see viable
use for <dialog> as a modal without the use of javascript are when
html is returned from the server and the open attribute is already
applied to the element <dialog open>. This then permits the dialog to be
closed with both <esc> keypress and using a form with method="dialog".

# Running Locally

1. Clone Repository
2. within directory run `npx live-server`

# Resources

[MDN Dialog](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
MDN  Reference page

[Adam Argyle](https://web.dev/articles/building/a-dialog-component)
A very good resource for making stylish dialogs

[Chris Coyer - 2019](https://css-tricks.com/some-hands-on-with-the-html-dialog-element/)
Old, but good introduction to it, link to polyfill

[Click Backdrop to Close](https://stackoverflow.com/questions/25864259/how-to-close-the-new-html-dialog-tag-by-clicking-on-its-backdrop)
How to close the dialog clicking on the backdrop

[Animate Out Dialog](https://codepen.io/geckotang/post/dialog-with-animation)
Old, but still valid, introduces adding a class to the dialog on close, and using `animationend` events to call `dialog.close()`

[Epic Easing](https://epiceasing.com)
Cubic Bezier generator with presets

[Creating an Accessible Modal Dialog](https://bitsofco.de/accessible-modal-dialog/)
Not related to <dialog> itself, but things to know when attempting to create a modal
