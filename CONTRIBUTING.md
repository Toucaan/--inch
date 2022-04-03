# Contributions:

PRs are super welcome. Please follow the rules specified below to submit new mappings for devices that aren't specified on the polyfill (`--inch.css`) or if they fail to fall into a catchAll().

1. One mapping per PR. Only one mapping to match a device to its `pixels:--inch` ratio is allowed.
2. Provide full resolution (under About OS/My Computer) of the device, year, browser(s) tested, and the underlying operating system. 
3. Make sure that your submitted mapping isn't already included on the accepted master. 

## How to test:

1. Clone the repo.

```
  $ git clone https://github.com/bookiza/--inch.git && cd --inch
```

2. Install dependencies.

```
  $ npm install
```
3. Run `npm run start`

```
  $ npm run start
```

4. Open the browser and navigate to `http://localhost:3000/`

The first square with the classname `square` will appear in the shape of a red square _only_ if there is a valid mapping for your machine. 

This square is supposed to measure 1 inch physically. Feel free to change the dimensions of the element `div.square` and resize until it measures an inch. 

Use a physical ruler to test on the screen. 

Once you have obtained the value of `--inch` for your device, you can submit it through PR for merge to the master branch.


```
/* 13.3-inch MBP, 2012, (1280 x 800px) */
@media (resolution: 96dpi) and (device-width: 1280px) {
  :root {
    --inch: 116px;
  }
}
```

The second square on the page has a specified dimension of `1in`, but since the implementation of `in` unit in CSS is _usually_ wrong, it will show the quantum of error that there is between the implementation and the actual standard unit.

Machines with higher dpi or up/downscaling will show more difference between a real inch and the css inch, for example.

### Issues: 

Raise an issue if you need help with the polyfill or if you have a question.