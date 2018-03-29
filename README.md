
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

All the configuration is done in the `_config.yml` file. Set `extensions` and `directories` to restrict the content you want to show. Set `style`, `truncate` and `html_link` to modify the presentation look.

Example to only show `pdf` and `md` files from the `Papers` directory in a `list` truncated to `60` chars and with `html_link` for the `md` files :

```
style: list
extensions:
  - .pdf
  - .md
directories:
  - Papers
truncate: 60
html_link:
  - .md
```

## Who is using jeklist ?

<https://cryptorating.eu/whitepapers>

If you use jeklist, please add your link here and make a pull request

## License

This work is under MIT license

Copyright © 2017, [Florent Gallaire](https://f.gallai.re)
