---
title: Web Performance - Choosing the right WordPress theme
layout: default
description: 
---

<style>
small {display: block;}
table {font-size: 80%;}
th {text-align: left;}
th + td {text-align: right;}
.u-right, .u-passed, .u-goodEnough, .u-failed {text-align: right;}
.u-passed {color: green;}
.u-goodEnough {color: orange;}
.u-failed {color: red;}
</style>

# Web Performance - Choosing the right WordPress theme

If you're using WordPress as a CMS, the theme you choose will have major impact on how your site will perform in terms of SEO.

* commercial WordPress themes try to satisfy a wide variety of purposes
* in consequence they grow in functionality and size (aka framework bloat) 
* all that at the cost of web performance

Therefore, use a standard, simple, fast WordPress theme. Speed should have the highest priority for choosing and adapting a Wordpress theme.

## Testing themes

> NOTE
>
> many theme previews are supported by some kind of frontend optimization plugin (eg: autoptimize, w3totalcache), which (a) bundles CSS/JS files and (b) optimizes loading logics of (potentially render blocking) assets. - this, by itself, is generally good practice and you should do so too, but beware that this may skew performance based testing metrics. themes are then often sold off better as when used out of the box (as in 'unoptimized').
>
> indicators for plugin backed optimizations are bundled CSS and JS files, which very likely contain the name of the plugin within their file path.
>
> <img src="{{site.url}}/i/wp-themes-plugin-optimized-1.jpg" alt="Plugin optimized CSS bundling">
>
> <img src="{{site.url}}/i/wp-themes-plugin-optimized-2.jpg" alt="Plugin optimized CSS bundling">

When you found a theme of interest, pick two representative pages from within the preview site (eg: 1 detail page and 1 list page / but not the start page) - both pages should pass the following tests:


**Google Page Speed Insights**

* gain minimum score of 80 (still orange) / preferrably 90 (green)
* render a sensemaking screenshots for desktop and mobile


**webpagetest.org**
<small>Test settings: Dulles (US) or London (Atlantic / EU) with a Cable Connection</small>

* **Start Render (normalized):** 700ms / 1400ms max
* **Speed Index (normalized):** 1000ms / 2000ms max

> NOTE @normalized
> 
> when you compare two or more themes, the server performance of the preview sites might vary. to normalize the rendering metrics across multiple themes:
> * substract the measured TTFB from start render and speed index  
> * and add a fixed TTFB of e.g. 200ms to both values


**"JS turned off" Test**

* all above fold and main content must be visible on the site with JS turned off
* the whole site must be navigate-able with JS turned off


**Google Mobile Friendly Test**
<small>test if possible; if not blocked by robots.txt</small>

* green rating "Mobile Friendly"
* sensemaking screenshot


## Case Study 
test results of 2 randomly selected magazine/blog like themes


> NOTE
> 
> theme previews are sometimes embedded via ```<iframe>```s which would skew our test results. use your browsers developer tools to get the embedded URL and use that one for testing.
>  
> **Demo URL:** <https://mythemeshop.com/themes/schema-lite/> (where the theme is embedded)
>
> **Test URL:** <https://demo.mythemeshop.com/schema-lite/> (direct accessible URL)



### Theme #1
* **List Page:** <https://demo.mythemeshop.com/schema-lite/category/business/>
* **Detail Page:** <https://demo.mythemeshop.com/schema-lite/lorem-ipsum-dolor-sit-amet-consectetur-adipisicing-elit/>


### Theme #2
* **List Page:** <https://demos.shapingrain.com/aspen1/category/lifestyle/>
* **Detail Page:** <https://demos.shapingrain.com/aspen1/2018/09/29/in-search-of-the-perfect-coffee-in-downtown-manhattan/>

<h3>Google Page Speed Insights</h3>
<table>
  <thead>
    <tr>
      <th>List Page (Theme #1)</th>
      <td class="u-passed">passed / good enough</td>
      <th>List Page (Theme #2)</th>
      <td class="u-failed">failed</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="2"><img src="{{site.url}}/i/lp-1-psi.jpg" alt=""></td>
      <td colspan="2"><img src="{{site.url}}/i/lp-2-psi.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>Detail Page (Theme #1)</th>
      <td class="u-passed">passed / good enough</td>
      <th>Detail Page (Theme #2)</th>
      <td class="u-failed">failed</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="2"><img src="{{site.url}}/i/dp-1-psi.jpg" alt=""></td>
      <td colspan="2"><img src="{{site.url}}/i/dp-2-psi.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<h3>webpagetest.org</h3>
<table>
  <thead>
    <tr>
      <th>List Page (Theme #1)</th>
      <td class="u-passed">passed / good enough</td>
      <th>List Page (Theme #2)</th>
      <td class="u-failed">failed</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Start Render (normalized)<br><small>Start Render - TTFB + Fixed TTFB (200ms)</small></td><td class="u-goodEnough">857 ms</td>
      <td>Start Render (normalized)<br><small>Start Render - TTFB + Fixed TTFB (200ms)</small></td><td class="u-goodEnough">1112 ms</td>
    </tr>
    <tr>
      <td>Speed Index (normalized)<br><small>Start Render - TTFB + Fixed TTFB (200ms)</small></td><td class="u-passed">871 ms</td>
      <td>Speed Index (normalized)<br><small>Start Render - TTFB + Fixed TTFB (200ms)</small></td><td class="u-failed">2089 ms</td>
    </tr>
    <tr>
      <td colspan="2"><img src="{{site.url}}/i/lp-1-wpt.jpg" alt=""></td>
      <td colspan="2"><img src="{{site.url}}/i/lp-2-wpt.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>Detail Page (Theme #1)</th>
      <td class="u-goodEnough">good enough</td>
      <th>Detail Page (Theme #2)</th>
      <td class="u-goodEnough">good enough</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Start Render (normalized)<br><small>Start Render - TTFB + Fixed TTFB (200ms)</small></td><td class="u-goodEnough">878 ms</td>
      <td>Start Render (normalized)<br><small>Start Render - TTFB + Fixed TTFB (200ms)</small></td><td class="u-goodEnough">1112 ms</td>
    </tr>
    <tr>
      <td>Speed Index (normalized)<br><small>Start Render - TTFB + Fixed TTFB (200ms)</small></td><td class="u-goodEnough">1185 ms</td>
      <td>Speed Index (normalized)<br><small>Start Render - TTFB + Fixed TTFB (200ms)</small></td><td class="u-goodEnough">1429 ms</td>
    </tr>
    <tr>
      <td colspan="2"><img src="{{site.url}}/i/dp-1-wpt.jpg" alt=""></td>
      <td colspan="2"><img src="{{site.url}}/i/dp-2-wpt.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<h3>JS on/off</h3>
<table>
  <thead>
    <tr>
      <th>List Page (Theme #1) - JS off</th>
      <td class="u-passed">passed</td>
      <th>List Page (Theme #2) - JS off</th>
      <td class="u-passed">passed</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="2"><img src="{{site.url}}/i/lp-1-js-off.jpg" alt=""></td>
      <td colspan="2"><img src="{{site.url}}/i/lp-2-js-off.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>Detail Page (Theme #1) - JS off</th>
      <td class="u-passed">passed</td>
      <th>Detail Page (Theme #2) - JS off</th>
      <td class="u-passed">passed</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="2"><img src="{{site.url}}/i/dp-1-js-off.jpg" alt=""></td>
      <td colspan="2"><img src="{{site.url}}/i/dp-2-js-off.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<h3>Google Mobile Friendly Test</h3>
<table>
  <thead>
    <tr>
      <th>List Page (Theme #1)</th>
      <td>n/a</td>
      <th>List Page (Theme #2)</th>
      <td class="u-passed">passed</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="2"><img src="{{site.url}}/i/lp-1-mft.jpg" alt=""></td>
      <td colspan="2"><img src="{{site.url}}/i/lp-2-mft.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>Detail Page (Theme #1)</th>
      <td>n/a</td>
      <th>Detail Page (Theme #2)</th>
      <td class="u-passed">passed</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="2"><img src="{{site.url}}/i/dp-1-mft.jpg" alt=""></td>
      <td colspan="2"><img src="{{site.url}}/i/dp-2-mft.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

