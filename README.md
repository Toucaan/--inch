# --inch

A global `--inch` polyfill using CSS variables.

This polyfill includes pin-pointed `pixels`:`--inch` mappings for commonly available hardware
according to their resolution `dpi` (default or "best" resolution) and `device-size`.
A full article on the reasoning behind this polyfill is printed here:

[https://bubblin.io/blog/inch](https://bubblin.io/blog/inch)

## Usage

### 1. Using `--inch` with Toucaan CSS Framework

If you're using the [Toucaan Mutative framework](https://toucaan.com), simply import `--inch.css`
at the top of your critical css like so:

```css
  /* Include `--inch` variable into the :root of the document using polyfill. */
  @import url('path/to/--inch.css') only screen;

  /* Portrait ⇋ landscape switch. */
  @import url('/dist/portrait.css') only screen and (orientation: portrait);
  @import url('/dist/landscape.css') only screen and (orientation: landscape);

  :root {
    /* Other CSS variables are specified here… */

  }
```

Now you can use the `--inch` variable on your stylesheets along the `portrait` or `landscape` axis,
like so:

```css
/* Portrait CSS */
@media (max-width: calc(2 * var(--inch)) {
  body{
    /*  Style for smartwatches or a very tiny mobile screen go here. */
  }
}

@media (min-width: calc(2.000000000001 * var(--inch)) and (max-width: calc(4 * var(--inch))) {
  body{
    /* Smartphones and phablets in portrait mode.*/
  }
}

@media (min-width: calc(4.000000000001 * var(--inch))) and (max-width: calc(8 * var(--inch))) {
  body{
    /* Tablets and larger menu surfaces in portrait mode.*/
  }
}

/* …and so on. */

```

### Extras

The following absolute units are available inside the global `:root` of your webpage along with `--inch`:

```css
:root {
  --centimeters: calc(2.54 * var(--inch));
  --millimeters: calc(25.4 * var(--inch));
  --meters: calc(2.54 * var(--inch) / 100);
  --feet: calc(12 * var(--inch));
  --thou: calc(var(--inch) / 1000); /* …because why not!? */
}
```

Now you can scale your UX/UI from, the tiniest viewport on the planet (the Apple Watch) to the largest
screens and projectors that there are in physical units.

Read more about Intrinsic Web Design and a new baseline reset on Toucaan's [documentation](https://www.toucaan.com/docs/introduction).

### 2. Using `--inch` with Bootstrap, Bulma, Tailwind:

Nearly all the major CSS frameworks use a reset or [normalize.css](https://github.com/necolas/normalize.css/) under the hood.

Since the `--inch` polyfill is aimed at intrinsic web design using physical units, I am not sure how it
would behave with the traditional frameworks with traditional resets. My general recommendation is to
avoid using the `--inch` variable with older CSS frameworks.

But if try you must, then the following line on the `<head></head>` should suffice:

```html
<link rel="stylesheet" href="path/to/css/--inch.css">
```

Please note that `--inch` variable is different from the CSS inch used in print which is usually hardcoded at `1in: 96px`.

### 3. Using `--inch` with generic CSS:

The `--inch` polyfill is also ideal if you are not using any style framework at all and want to
support and scale along new devices like the Apple Watch or a hi-res OLED TV.
Works great if you're willing to build your designs ground up using vanilla css.

> @import url('path/to/--inch.css') only screen;

### References

1. https://caniuse.com/#feat=css-media-resolution

2. https://caniuse.com/#search=device-width

3. https://sebastien-gabriel.com/designers-guide-to-dpi/

4. https://www.w3.org/Style/Examples/007/units.en.html

5. https://bubblin.io/blog/web-design-recommendations-for-the-apple-watch
