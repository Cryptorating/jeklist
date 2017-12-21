
# jeklist

Build a Jekyll list of your static content in seconds, without touching the command line

## Installation

1) Fork this repository

2) Go to Settings->GitHub Pages, select `master branch` then click on the `Save` button

With the GitHub Pages activation, your site is published at https://yourusername.github.io/jeklist

## Change theme

1) Go to Settings->GitHub Pages then click on the `Change theme` button

2) Select one of the available themes then click on the `Select theme` button

## Configuration

All the configuration is done in the `index.md` front matter. Set `extensions` and `directories` to restrict the content you want to show.

Example to only show `pdf` files from the `Papers` directory:

```
---
extensions:
   - .pdf
directories:
   - Papers 
---
```

## Who is using jeklist ?

https://cryptorating.eu/white_papers

If you use jeklist, please add your link here and make a pull request

## License

This work is under MIT license

Copyright © 2017, [Florent Gallaire](https://f.gallai.re)
