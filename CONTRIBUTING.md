# Contributions:

PRs are super welcome. Please follow the rules specified below to submit new mappings for devices that aren't specified on `--inch.css` but fall into a catchAll().

1. One mapping per PR. Only one mapping to match a device to its `pixels:--inch` ratio is allowed.
2. Provide full resolution (under About OS/My Computer) of the device, year, browser(s) tested and operating system. 
3. Make sure that your submitted mapping isn't already included on the accepted master. 

## How to test:

The first square with className `square` will appear in shape of a square _only_ if the mapping for your machine is accurate. This square is supposed to measure 1 inch physically.

```
@media (resolution: 96dpi) and (device-width: 1280px) {
  :root {
    --inch: 116px;
  }
}

```

The second square has specified dimensions of `1in` but since the `in` is wrong, it will show what % of error there is on on a given system. Machines with higher dpi or up/downscaling will show more difference between a real inch and the css inch. 