---
layout: base
title: Get Started
subtitle: Easy ways to get !fa-name! !fa-version! onto your website
jumbotron-icon: cogs
---

## Use a CDN

The simplest way to get Fork Awesome in your project is to copy the following
line within the `<head>` tag of your HTML source files. The check the [examples]
to start displaying icons.

```html
<link rel="stylesheet" href="{{ site.forkawesome.cdn.url_prefix }}/{{ site.forkawesome.name | slugify }}@{{ site.forkawesome.version }}/css/fork-awesome.min.css" integrity="{{ site.forkawesome.cdn.integrity }}" crossorigin="anonymous">
```

Thanks to [{{ site.forkawesome.cdn.name }}] for providing the CDN for {{ site.forkawesome.name }}

[{{ site.forkawesome.cdn.name }}]: {{ site.forkawesome.cdn.package_prefix }}/{{ site.forkawesome.name | slugify }}

---

## Download &amp; Customize

{% include download-button-modal.html style="pull-right" %}

#### Want to manage and host Fork Awesome assets yourself? You can download, customize, and use the icons and default styling manually. Both CSS and CSS Preprocessor (Sass and Less) formats are included.

### Using CSS
1. Copy the entire `fork-awesome` directory into your project.
2. In the `<head>` of your HTML, reference the location to your
   `font-awesome.min.css`.
   ```html
   <link rel="stylesheet" href="/path/to/fork-awesome/css/fork-awesome.min.css">
   ```
3. Check out the [examples] to start using Fork Awesome!

### Using Sass or Less

Use this method to customize {{ site.forkawesome.name }}
{{ site.forkawesome.version }} using Less or Sass.
1. Copy the `fork-awesome/` directory into your project
2. Open your project's `fork-awesome/less/variables.less` or
   `fork-awesome/scss/_variables.scss` and edit the `@fa-font-path` or
   `$fa-font-path` variable to your font directory.

   ```scss
     @fa-font-path:   "../font";
   ```

   <p class="alert alert-info">
     <i class="fa fa-info-circle"></i>
     The font path is relative from your compiled CSS directory.
   </p>

3. Re-compile your Less or Sass if using a static compiler. Otherwise, you should be good to go.
4. Check out the [examples] to start using Fork Awesome!

---

### Use {{ site.forkawesome.name }} in your C or C++ applications

Juliette Foucault has created a little library called [IconFontCppHeaders] to
help use a few icon fonts in your C or C++ projects and Fork Awesome is part
of it.

```c
#include "IconsForkAwesome.h"
```

[IconFontCppHeaders]: https://github.com/juliettef/IconFontCppHeaders

---

## More Information

#### Validators

In order to provide the best possible experience to old and buggy browsers,
Fork Awesome uses [CSS browser hacks] in several places to target special CSS to
certain browser versions in order to work around bugs in the browsers
themselves. These hacks understandably cause CSS validators to complain that
they are invalid. In a couple places, we also use bleeding-edge CSS features
that aren't yet fully standardized, but these are used purely for progressive
enhancement.

These validation warnings don't matter in practice since the non-hacky portion
of our CSS does fully validate and the hacky portions don't interfere with the
proper functioning of the non-hacky portion, hence why we deliberately ignore
these particular warnings.

[Getting started - Validators] by [Bootstrap Team] is licensed under [CC BY 3.0]

[CSS browser hacks]: //browserhacks.com/
[Getting started - Validators]: //getbootstrap.com/getting-started/#support-validators

#### Internet Explorer 8 and @font-face

Internet Explorer 8 has some issues with `@font-face` when combined with
`:before`. {{ site.forkawesome.name }} uses that combination. If a page is
cached, and loaded without the mouse over the window (i.e. hit the refresh
button or load something in an iframe) then the page gets rendered before the
font loads.  Hovering over the page (body) will show some of the icons and
hovering over the remaining icons will show those as well. See
[Font Awesome issue #954] for details.

[Getting started - Internet Explorer 8 and @font-face] by [Bootstrap Team] is
licensed under [CC BY 3.0]

[Getting started - Internet Explorer 8 and @font-face]: http://getbootstrap.com/getting-started/#support-ie8-font-face
[Font Awesome issue #954]: https://github.com/FortAwesome/Font-Awesome/issues/954

#### Need Internet Explorer 7 Support?

Sorry, {{ site.forkawesome.name }} {{ site.forkawesome.version }} does not
support Internet Explorer 7, but an older version (v3.2.1) of
{{ site.fontawesome.name }} does (if you can still find it).

[examples]: examples
[Bootstrap Team]: //getbootstrap.com/about/#team
[CC BY 3.0]: //creativecommons.org/licenses/by/3.0/
