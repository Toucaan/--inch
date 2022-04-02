# --inch

A global `--inch` polyfill for accurate _digital physical standard and imperial_ units on CSS. This polyfill includes exact `pixels`:`--inch` pairings (or mappings) for the commonly available consumer hardware.

Each pairing maps the device resolution `dpi` (or the _default_ or the 'best' resolution) to the actual size of an inch measured physically.

Full article on the reasoning behind this polyfill is [printed](https://bubblin.io/blog/inch) on the official blog.

> Please note that the `--inch` variable on the polyfill is different from the standard CSS inch used in the print industry that is usually hardcoded at `1in: 96px`.


## Usage

### 1. Using `--inch` with Toucaan CSS Framework

If you are using the [Toucaan Mutative framework](https://toucaan.com), add `--inch.css` polyfill at the top of your critical css like so:

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

Assuming that support for var() and calc() functions will eventually land in media queries, you can then use the `--inch` variable on your stylesheet along the `portrait` or `landscape` axis of the [intrinsic web design](https://bubblin.io/blog/a-css-router), like so:

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

### Contribute

Head over [here](https://github.com/Toucaan/--inch/blob/master/CONTRIBUTING.md). 🙏🏻

### Extras

The following additional absolute units are also available within the global `:root` of your webpage/application:

```css
:root {
  --centimeters: calc(2.54 * var(--inch));
  --millimeters: calc(25.4 * var(--inch));
  --meters: calc(2.54 * var(--inch) / 100);
  --feet: calc(12 * var(--inch));
  --thou: calc(var(--inch) / 1000); /* …because why not!? */
}
```

Great! Scale your UI from the tiniest viewport of the Apple Watch to the giant screen of a projector using physical inches. Read more about Intrinsic Web Design and a [new baseline reset](https://bubblin.io/blog/baseline-css) on [Toucaan](https://www.toucaan.com/docs/introduction).

### 2. Using `--inch` with Bootstrap, Bulma, or Tailwind:

Nearly all the well-known CSS frameworks are responsive in nature and utilize what is called a `reset.css` or [normalize](https://github.com/necolas/normalize.css/) under the hood. Since the `--inch` polyfill is riveted for _intrinsic web design_ using physical units, it is unlikely to function as expected with those older frameworks. 

My general recommendation is to avoid using the `--inch` polyfill with older CSS frameworks.

#### …but I want to try with Tailwind!
Sure. If try you must, then the following line on the `<head></head>` would suffice:

```html
<link rel="stylesheet" href="path/to/css/--inch.css">
```

Do share your results with us on [GitHub](https://github.com/Toucaan/--inch/discussions)


### 3. Using `--inch` with generic CSS:

The `--inch` polyfill is also ideal if you are not using any css framework on your app. Works great with vanilla css!

> @import url('path/to/--inch.css') only screen;

### References

1. https://caniuse.com/#feat=css-media-resolution

2. https://caniuse.com/#search=device-width

3. https://sebastien-gabriel.com/designers-guide-to-dpi/

4. https://www.w3.org/Style/Examples/007/units.en.html

5. https://bubblin.io/blog/web-design-recommendations-for-the-apple-watch