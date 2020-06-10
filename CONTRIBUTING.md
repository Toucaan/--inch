# Contributions:

PRs are super welcome. Please follow the rules specified below to submit new mappings for devices that aren't specified on `--inch.css` but fall into a catchAll().

1. One mapping per PR. Only one mapping to match a device to its `pixels:--inch` ratio is allowed.
2. Provide full resolution (under About OS/My Computer) of the device, year, browser(s) tested and operating system. 
3. Make sure that your submitted mapping isn't already included on the accepted master. 

## How to test:

The first square with className `square` will appear in shape of a square _only_ if the mapping for your machine is accurate. This square is supposed to measure 1 inch physically.

```
/* 13.3-inch MBP, 2012, (1280 x 800px) */
@media (resolution: 96dpi) and (device-width: 1280px) {
  :root {
    --inch: 116px;
  }
}
```

The second square has a specified dimension of `1in` but since the `in` unit is wrong, it will show the quantum of error there is on a given machine. Machines with higher dpi or up/downscaling will show more difference between a real inch and the css inch, for example.

### Steps: 

```
$ git clone https://github.com/bookiza/--inch.git && cd --inch

$ npm install

$ npm run start
```

The page will load at `localhost:3000` with just the two squares or one depending on the machine.


