# --inch

A global `--inch` polyfill using CSS variables.

This file includes pin-pointed pixels:`--inch` mappings for commonly available hardware
according to their resolutionary `dpi` and `device-size`.

## Usage

### 1. `--inch` with Toucaan CSS Framework

If you're using [Toucaan Mutative](https://toucaan.com), simply import `--inch.css`
at the top of your critical css like so:

```css
	/* Incllude `--inch` at :root using polyfill. */
  @import url('path/to/--inch.css') only screen;

  /* Portrait ⇋ landscape switch. */
  @import url('/dist/portrait.css') only screen and (orientation: portrait);
  @import url('/dist/landscape.css') only screen and (orientation: landscape);

	/* Other style variables go below… */

```

Now you can use `--inch` on your stylesheets along `portrait` or `landscape` axis
like in the real world!
