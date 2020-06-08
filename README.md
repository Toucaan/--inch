# --inch

A global `--inch` polyfill using CSS variables.

This polyfill includes pin-pointed `pixels`:`--inch` mappings for commonly available hardware
according to their resolutionary `dpi` (default or "best" resolution) and `device-size`.
Full discussion about the reasoning behind this polyfill is available here:

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

Now you can use the `--inch` variable on your stylesheets along the `portrait` or `landscape` axis
like so:

```css
/* Portrait CSS */
@media only screen and (max-width: calc(2 * var(--inch)) {
  body{
    /*  Style for smartwatches or a very tiny mobile screen go here. */
  }
}

@media only screen and (min-width: calc(2.000000000001 * var(--inch)) and (max-width: calc(4 * var(--inch))) {
  body{
    /* Smartphones and phablets in portrait mode.*/
  }
}

@media only screen and (min-width: calc(4.000000000001 * var(--inch))) and (max-width: calc(8 * var(--inch))) {
  body{
    /* Tablets and larger menu surfaces in portrait mode.*/
  }
}

/* …and so on. */

```

Scale your UX/UI along the _portrait_ orientation from the tiniest viewport
on the planet (Apple Watch) to the largest screen (mounted vertically) there is.
Apply the same rules to scale the UI orthogonally along landscape
orientation from the tiniest screen to the largest TVs and projectors on the web.

Read more about Intrinsic Web Design and Baseline RResets on Toucaan [documentation](https://www.toucaan.com/docs/introduction).

### 2. Using `--inch` with Bootstrap, Bulma, Tailwind:

### 3. Using `--inch` with generic CSS:

### References

1. https://caniuse.com/#feat=css-media-resolution

2. https://caniuse.com/#search=device-width

3. https://sebastien-gabriel.com/designers-guide-to-dpi/

4. https://www.w3.org/Style/Examples/007/units.en.html

5. https://bubblin.io/blog/web-design-recommendations-for-the-apple-watch



