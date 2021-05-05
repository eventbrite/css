# Table of Contents
1. [Compiling SCSS](#compiling-scss)
2. [Variables](#variables)
3. [Best Practices](#best-practices)

## Compiling SCSS
TODO: needs updating

## Variables

With SCSS we can define reusable variables to store meaningful values like brand colors and font sizes. This allows us to:

1.  Give meaning to otherwise generic values. Instead of `#f16924` and `#4661a3`, we have `$brand-color-orange` and `$facebook-brand-color`.
2.  Change values in one place.
3.  Properly scope changes when we’re using the same values for different contexts. Let’s say Eventbrite’s brand orange shares the same hex value as Facebook’s brand orange (let’s say). If Facebook changes their brand color to blue, it becomes very difficult to programmatically update the areas where we’re using `#f16924` for Facebook and not also for Eventbrite.

    Now if we want to update a value but only in certain contexts, we can limit our changes to a specific variable (in this case `$facebook-brand-color`) instead of all instances of the value.

Currently we store our site-wide variables in **styleguide/sass/base/\_settings.scss** in our styleguide repo and import them where needed:

``` sourceCode
// In base/_settings.scss
$default-border-color: #dedede;
$large-border-radius: 5px;
```

``` sourceCode
// In modules/_pod.scss
@import "base/_settings.scss";
@import "compass/css3/border-radius";

.pod {
    border: 1px solid $default-border-color;
    @include border-radius($large-border-radius);
}
```

## Coding Standards

We maintain a [SCSS-Lint Config] that defines our preferred rules for coding Sass files. In general:

-   4 Space Indentation
-   Spaces between braces, colons, parameters, etc: (e.g. `background-color: rgb(255, 255, 255)`)
-   [Statement Ordering]:  
    -   @extend
    -   @include
    -   properties
    -   @include with inner content (.e.g. `@include responds-to($large-only) { ... }`)
    -   nested rules

To Install [SCSS-Lint]:

    gem install --no-rdoc --no-ri scss-lint -v 0.30.0

You can also usually find a plugin for your editor of choice. SublimeText3 has [SublimeLinter-contrib-scss-lint]. This will ensure your code is linted as you edit.

  [SCSS-Lint Config]: https://github.com/eventbrite/core/blob/master/django/media/django/compass/sass/.scss-lint.yml
  [Statement Ordering]: https://github.com/causes/scss-lint/blob/master/lib/scss_lint/linter/README.md#declarationorder
  [SCSS-Lint]: https://github.com/causes/scss-lint
  [SublimeLinter-contrib-scss-lint]: https://sublime.wbond.net/packages/SublimeLinter-contrib-scss-lint
