# --inch

A global `--inch` polyfill using CSS variables.

This file includes pin-pointed pixels:`--inch` mappings for commonly available hardware
according to their resolutionary `dpi` and `device-size`.

## Usage

### 1. Using `--inch` with Toucaan CSS Framework

If you're using the [Toucaan Mutative framework](https://toucaan.com), simply import `--inch.css`
at the top of your critical css like so:

```css
  /* Incllude `--inch` at :root using polyfill. */
  @import url('path/to/--inch.css') only screen;

  /* Portrait ⇋ landscape switch. */
  @import url('/dist/portrait.css') only screen and (orientation: portrait);
  @import url('/dist/landscape.css') only screen and (orientation: landscape);

  /* Other :root variables are specified under this line… */
  :root {
    --bu: 1vmin;
    --white: rgba(255, 255, 255, 1);
    --black: rgba(0, 0, 0, 1);

  /* Font familia */
    --sans-serif: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    --system: system-ui, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, Oxygen, Ubuntu, Cantarell, Droid Sans, Helvetica Neue, Fira Sans, sans-serif!important;
    --monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  }


```

Now you can use `--inch` on your stylesheet along the `portrait` or `landscape` axis
like a champion!

```css
/* Portrait CSS */
@media only screen and (max-width: calc(2 * var(--inch)) {
  body{
    /*  All the style for a smartwatch or a very tiny mobile screen
        go in here. We don't use pixels for an Apple Watch because
        its viewport is just too small for the pixels to scale correctly.
        Also, hardcoded values on @media-query breakpoints is somewhat
        antipattern now! */
    /*  Read web designing for the Apple Watch at: https://bubblin.io/blog/web-design-recommendations-for-the-apple-watch */
    /*  Read more at https://bubblin.io/blog/toucaan-introduction */
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

/* and so on…*/

```

### 2. Using `--inch` with Tailwind CSS:

### 3. Using `--inch` with Bootstrap:

### 4. Using `--inch` with Bulma:

### 5. Using `--inch` with generic CSS:


