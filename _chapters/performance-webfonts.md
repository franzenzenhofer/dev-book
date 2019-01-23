---
title: Web Performance - Web Font Optimization
layout: default
description: Custom web fonts are critical rendering assets. A proper loading strategy and font file optimization can improve page load and rendering times.
---

# Web Font Optimization

Custom web fonts loaded using @font-face are render critical assets:

* text is rendered invisible until particular font files have been downloaded
* font file requests are delayed until the DOM and CSSOM are constructed (ie: @font-face in an external stylesheet introduce a critical request chain)
* size, format and number of web fonts directly impact time to download

## Asset Optimization - Font File Formats and Unicode-range subsetting

The size of a font file is determined by its format and the supported unicode range (i.e. amount of glyphs for e.g. language specific special charactars, like Latin or Cyrillic).

* provide only modern and compressed font file formats (WOFF and WOFF2) 
* subset the unicode-range to only include characters for a specific language

For historical reasons (browser support) there are now four main font file formats (EOT, TTF, WOFF, WOFF2):

* EOT and TTF are uncompressed formats (and need gzip compression)
* WOFF and WOFF2 are compressed by design (whereas the latter has even stronger compression)

The unicode range of a font can be subsetted (to only include characters for a specific language), which can drastically decrease file size of the font.

* use the unicode-range descriptor of the @font-face() rule
* or use a web font generator to only include a certain subset

```css
@font-face {
  font-family: 'Font Name';
  font-style: normal;
  font-weight: 400;
  src: local('Font name'),
       url('/fonts/font-name.woff2') format('woff2'),
       url('/fonts/font-name.woff') format('woff')
  unicode-range: U+000-5FF; /* Latin glyphs */
}
```
s
