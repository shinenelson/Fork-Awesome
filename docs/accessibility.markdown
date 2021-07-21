---
layout: base
title: Accessibility
subtitle: Make your icons awesome for all of your users
jumbotron-icon: universal-access
---

### Icons are symbols that can convey a ton of information and really help people comprehend directions, signs, and interfaces. It's important that we create and use them so that they can reach the largest amount of people possible.

---

#### About Icon Fonts &amp; Accessibility

Modern versions of assistive technology, like screen readers, will
read CSS generated content (how Fork Awesome icons are rendered), as
well as specific Unicode characters. When reading our default markup
for rendering icons, assisistive technology may have the following
problems :
- The assistive technology may not find any content to read out to a user
- The assistive technology may read the unicode equivalent, which
  could not match up to what the icon means in context, or worse is
  just plain confusing

---

## Using {{ site.forkawesome.name }} with Accessibility in mind

When using icons in your UI, there are manual techniques and ways to
help assistive technology either ignore or better understand
{{ site.forkawesome.name }}.

### Icons used for pure decoration or visual styling

If you're using an icon to add some extra decoration or branding, it
does not need to be announced to users as they are navigating your
site or app aurally. Additionally, if you're using an icon to visually
re-emphasize or add styling to content already present in your HTML,
it does not need to be repeated to an assistive technology-using user.
You can make sure this is not read by adding the `aria-hidden="true"` to
your {{ site.forkawesome.name }} markup.

```html
<i class="fa fa-fighter-jet" aria-hidden="true"></i>
```
<small class="text-muted">an icon being used as pure decoration</small>

```html
<h1 class="logo">
  <i class="fa fa-fork-awesome" aria-hidden="true"></i>
  Fork Awesome, a fork of the iconic font and CSS toolkit
</h1>
```
<small class="text-muted">an icon being used as a logo</small>

```html
<a href="https://github.com/FortAwesome/Font-Awesome">
  <i class="fa fa-github" aria-hidden="true"></i>
  View this project's code on Github
</a>
```
<small class="text-muted">an icon being used in front of link text</small>

### Icons with semantic or interactive purpose

If you're using an icon to convey meaning (rather than only as a
decorative element), ensure that this meaning is also conveyed to
assistive technologies. This goes for content you're abbreviating via
icons as well as interactive controls (buttons, form elements,
toggles, etc.). There are a few techniques to accomplish this:

#### If an icon **does not** represent an interactive element

The simplest way to provide a text alternative is to use the
`aria-hidden="true"` attribute on the icon and to include
the text with an additional element, such as a
`<span>`, with appropriate CSS to visually hide the
element while keeping it accessible to assistive technologies. In
addition, you can add a `title` attribute on the icon to
provide a tooltip for sighted mouse users.

```html
<dl>
  <dt>
    <i class="fa fa-car" aria-hidden="true" title="Time to destination by car"></i>
    <span class="sr-only">Time to destination by car:</span>
  </dt>
  <dd>4 minutes</dd>

  <dt>
    <i class="fa fa-bicycle" aria-hidden="true" title="Time to destination by bike"></i>
    <span class="sr-only">Time to destination by bike:</span>
  </dt>
  <dd>12 minutes</dd>
</dl>
```
<small class="text-muted">an icon being used to communicate travel methods</small>

```html
<i class="fa fa-hourglass" aria-hidden="true" title="60 minutes remain in your exam"></i>
<span class="sr-only">60 minutes remain in your exam</span>

<i class="fa fa-hourglass-half" aria-hidden="true" title="30 minutes remain in your exam"></i>
<span class="sr-only">30 minutes remain in your exam</span>

<i class="fa fa-hourglass-end" aria-hidden="true" title="0 minutes remain in your exam"></i>
<span class="sr-only">0 minutes remain in your exam</span>
```
<small class="text-muted">an icon being used to denote time remaining</small>

#### If an icon **does** represent an interactive element

In the case of focusable interactive elements, there are various
options to include an alternative text or label to the element,
without the need for any visually hidden `<span>` or similar. For
instance, simply adding the `aria-label` attribute with a text
description to the interactive element itself will be sufficient to
provide an accessible alternative name for the element. If you need to
provide a visual tooltip on mouseover/focus, we recommend additionally
using the `title` attribute or a [custom tooltip] solution.

[custom tooltip]: https://github.com/chinchang/hint.css

```html
<a href="path/to/shopping/cart" aria-label="View 3 items in your shopping cart">
  <i class="fa fa-shopping-cart" aria-hidden="true"></i>
</a>
```
<small class="text-muted">an icon being used to communicate shopping cart state</small>

```html
<a href="#navigation-main" aria-label="Skip to main navigation">
  <i class="fa fa-bars" aria-hidden="true"></i>
</a>
```
<small class="text-muted">an icon being used as a link to a navigation menu</small>

```html
<a class="btn btn-danger" href="path/to/settings" aria-label="Delete">
  <i class="fa fa-trash-o" aria-hidden="true" title="Delete this item?"></i>
</a>
```
<small class="text-muted">an icon being used as a delete button's
symbol with a `title` attribute to provide a native mouse tooltip</small>

<p class="alert alert-info">
  <i class="fa fa-info-circle"></i>
  See more
  <a href="examples#accessible">examples</a>
  of how to add accessibility-minded icons into your UI.
</p>

## Other cases and information

While the scenarios and techniques here help avoid some serious issues
and confusion, they are not exhaustive. There are many complex
contexts and use cases when it comes to accessibility, such as users
with low vision who need a high color contrast ratio to see UI. There
are some great tools and resources to learn from and work on these
issues out there. Here are a few reads we recommend :
* [Bulletproof Accessible Icon Fonts - Filament Group, Inc.]
* [HTML for Icon Font Usage - CSS-Tricks]
* [The Great Icon Debate: Fonts Vs SVG - SitePoint]
* [Contrast Ratio: Easily calculate color contrast ratios. Passing WCAG was never this easy!]

We'll continue to work on these under the larger topic of
accessibility, but in the meantime, let us know of any [issues]. 

[Bulletproof Accessible Icon Fonts - Filament Group, Inc.]: https://www.filamentgroup.com/lab/bulletproof_icon_fonts.html
[HTML for Icon Font Usage - CSS-Tricks]: https://css-tricks.com/html-for-icon-font-usage/
[The Great Icon Debate: Fonts Vs SVG - SitePoint]: https://www.sitepoint.com/icon-fonts-vs-svg-debate/
[Contrast Ratio: Easily calculate color contrast ratios. Passing WCAG was never this easy!]: https://contrast-ratio.com/
[issues]: community#reporting-bugs
