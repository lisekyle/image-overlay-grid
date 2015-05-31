# Jellyvision Audition
**Modern UI Engineer**

This framework places text over an image on a vertical and horizontal grid. It uses [BEM notation](https://en.bem.info/method/definitions/), [SassScript](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#control_directives__expressions), and super-fun-happy Daria quotes.

Each image overlay section inherits a `$max-width` variable (which can be changed based on the image size). In this scenario, all our images are 960px.

Our columns and rows are set with `$columns` and `$rows` (in `_variables.scss`), and are then calculated and complied with this loop:

```
@for $i from 1 through $columns // loop defines columns. c1, c2, c3 . . .
        .#{$column-prefix+$i}
            margin-left: 100% / $columns * ($i - 1)

    $vertical-grid: true !default
    @if $vertical-grid true.
    @for $i from 1 through $rows // loop defines rows. r1, r2, r3 . . .
        .#{$row-prefix+$i}
            top: 100% / $rows * ($i - 1)
```

This makes it very easy to assign classes to our `image-overlay__text` block. For example, if we want our text to be placed 3 columns over (30%) and 5 rows down (50%) we would write `image-overlay__text c3 r5`. Easy peasy!

