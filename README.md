# --inch
A global `--inch` poly-fill for accurate implementation of standard or imperial physical units of measurement using css custom properties. This poly-fill includes a list of exact `pixels`:`--inch` pairings (or mappings) for the _commonly_ available consumer hardware.

### Pairing?
A pairing maps the device resolution `dpi` to the actual size of an inch that has been measured physically using a scale. A detailed article on how this works is [printed](https://bubblin.io/blog/inch) on the Bubblin blog.


## Usage

### 1. Using `--inch` with Toucaan 
If you are using [Toucaan](https://toucaan.com), you can simply add the `--inch.css` poly-fill as part of the utility variables adopted in the critical css region of your webpage. Alternatively, `--inch` can also be directly imported into the `env` source of the framework by simply copying the poly-fill files into the appropriate folder.

```css
  /* Import the `--inch` variable. */
  @import url('path/to/--inch.css') only screen;

  /* Portrait ⇋ landscape switch. */
  @import url('/dist/portrait.css') only screen and (orientation: portrait);
  @import url('/dist/landscape.css') only screen and (orientation: landscape);

  :root {
    /* Other CSS variables are specified here… */

  }
```

#### Additional Units

The following absolute units can also be used with the `inch` variable:

```css
:root {
  /* Import the `--inch` variable. */
  @import url('path/to/--inch.css') only screen;

  --centimeters: calc(2.54 * var(--inch));
  --millimeters: calc(25.4 * var(--inch));
  --meters: calc(2.54 * var(--inch) / 100);
  --feet: calc(12 * var(--inch));
  --thou: calc(var(--inch) / 1000); /* …because why not!? */
}
```

### 2. Using the `--inch` unit with Bootstrap, Bulma, or Tailwind:

It might work, but my general recommendation is to avoid using the `--inch` poly-fill with any of the responsive css frameworks. Mainly because:

1. The poly-fill is experimental in nature.
2. Responsive design is rooted in the use of standard design units like `px`, `em` etc.

### 3. Using the `--inch` variable with plain css:
The `--inch` poly-fill is great for apps that do not use any css framework. It works great with vanilla css!

### NOT FOR PRODUCTION USE
Although this poly-fill has a certain level of support for common consumer devices already, it certainly is NOT SUITABLE FOR PRODUCTION USE at all. At least not yet.

Assuming support, you will be able to use the `--inch` on your styles, like so:

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

### Contribution

Contributions of new mappings are always welcome. Head over [here](https://github.com/Toucaan/--inch/blob/master/CONTRIBUTING.md) to learn how. 🙏🏻

### References

1. https://caniuse.com/#feat=css-media-resolution

2. https://caniuse.com/#search=device-width

3. https://sebastien-gabriel.com/designers-guide-to-dpi/

4. https://www.w3.org/Style/Examples/007/units.en.html

5. https://bubblin.io/blog/web-design-recommendations-for-the-apple-watch

Do share your thoughts on [GitHub](https://github.com/Toucaan/--inch/discussions)