---
title: Web Font Optimization
layout: default
description: Custom web fonts are critical rendering assets. A proper loading strategy and font file optimization can improve page load and rendering times.
---

# Web Font Optimization

Custom web fonts loaded using @font-face are render critical assets:

* text is rendered invisible until particular font files have been downloaded
* font file requests are delayed until the DOM and CSSOM are constructed (ie: @font-face in an external stylesheet introduce a critical request chain)
* size, format and number of web fonts directly impact time to download

## Avoid web fonts - Use a system font stack

* a system font stack is a list of generic, system-integrated UI-fonts of different operating systems
* generally the same as “web safe” fonts but mostly available in multiple font-weights (100-900)
* using a system font stack allows for more style variations than “web safe” fonts while not harming performance 

```css
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
}
```

## Asset Optimization - Font File Formats and Unicode-range subsetting

The size of a font file is determined by its format and the supported unicode range (i.e. amount of glyphs for e.g. language specific special charactars, like Latin or Cyrillic).

* provide only modern and compressed font file formats (WOFF and WOFF2) 
* subset the unicode-range to only include characters for a specific language

For historical reasons (browser support) there are now four main font file formats:

* EOT and TTF are uncompressed formats (and need gzip compression)
* WOFF and WOFF2 are compressed by design (whereas the latter has even stronger compression)
* Note: The order of font format specification matters, as browsers use the first format they support. Specifying `format('woff')` before `format('woff2')` would cause the browser to download the larger .woff file

```css
@font-face {
  font-family: 'Font Name';
  ...
  src: local('Font Name'),
       url('/fonts/font-name-regular.woff2') format('woff2'),
       url('/fonts/font-name-regular.woff') format('woff')
}
```

The unicode range of a font can be subsetted (to only include characters for a specific language), which can drastically decrease file size of the font.

* use the unicode-range descriptor of the @font-face() rule
* or use a web font generator to produce font files that only consist of a certain subset

```css
@font-face {
  font-family: 'Font Name';
  ...
  unicode-range: U+000-5FF; /* Latin glyphs */
}
```

## Optimize font loading and text rendering

Font file requests are delayed until after the render tree is constructed. In other words, if a @font-face() rule is defined in an external stylesheet, the stylesheet has to be downloaded and parsed first, before the font file request is issued. - By default browser don't render text until the font files have been downloaded.

* always self-host font files: any 3rd party integration adds network overhead
* use `local('Font Name')` in src list to avoid HTTP requests for fonts that are installed on a system
* use `font-display: swap` to avoid render blocking (and force browsers to display text in a fallback font until the particular font file arrives)
* ensure early font file download by using `<link rel="preload">`
* inline the `@font-face()` rule into the html to avoid critical request chains
* set long lasting browser cache directives (Cache-Control: max-age= / Expires)


```html
<link rel="preload" href="/fonts/font-name-regular.woff2" as="font" type="font/woff2" crossorigin>
<link rel="preload" href="/fonts/font-name-bold.woff2" as="font" type="font/woff2" crossorigin>

<style>
@font-face {
  font-family: 'Font Name';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: local('Font Name'),
       url('/fonts/font-name-regular.woff2') format('woff2'),
       url('/fonts/font-name-regular.woff') format('woff')
}
</style>

<style>
@font-face {
  font-family: 'Font Name';
  font-style: normal;
  font-weight: 600;
  font-display: swap;s
  src: local('Font Name'),
       url('/fonts/font-name-bold.woff2') format('woff2'),
       url('/fonts/font-name-bold.woff') format('woff')
}
</style>
```