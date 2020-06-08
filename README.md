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

/* 	and so on… */

```
Scale your UX/UI along portrait orientation from the tiniest viewport
on the planet to the largest screen there is mounted vertically.

Follow the same rules to scale your UI orthogonally along landscape
orientation from the tiniest screens to the largest projectors and TVs.

Read more about scaling UI and baseline resets on Toucaan [documentation](https://www.toucaan.com/docs/introduction).


### 2. Using `--inch` with Bootstrap, Bulma, Tailwind or other responsive CSS frameworks:



### 3. Using `--inch` with generic CSS:

## How does it work

## Contributing

