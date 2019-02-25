---
title: Web Performance - Choosing the right WordPress theme
layout: default
description: 
---


# Web Performance - Choosing the right WordPress theme

WordPress theme selection can have major impact on how your site performs within SEO and UX

* commercial WordPress themes try to satisfy a wide variety of purposes
* in consequence they grow in functionality and size (so called framework bloat) 
* at the cost of web performance

## Testing themes

pick two representative pages within a theme preview site (eg: 1 article detail page and 1 article list page)
both pages should pass the following tests:

**Google Page Speed Insights**

* minimum score of 80 (still orange) / preferrably 90 (green) + sensemaking screenshots for desktop and mobile


**webpagetest.org**

(test settings: Dulles, US or London (Atlantic), EU / Cable Connection)

* start render (normalized): 700ms (1400ms max)
* speed index (normalized): 1000ms (2000ms max)

> NOTE @normalized - as you can't control the server performance of theme preview sites, and it might differ from server to server:
> * substract the measured TTFB from start render and speed index and 
> * add a fixed TTFB of e.g. 200ms to both values


**"JS turned off" Test**

* above fold and main content must be visible on the site with JS turned off! 
* whole site must be navigate-able with JS turned off!


**Google Mobile Friendly Test**

(only if possible. ie: preview pages are often blocked by robots.txt)

* green rating "Mobile Friendly"
* sensemaking screenshot


## Case Study 

we randomly selected 2 themes:

### Theme #1

Demo URL: https://mythemeshop.com/themes/schema-lite/

Test URL: https://demo.mythemeshop.com/schema-lite/

note: theme previews are often embedded via an ```<iframe>``` which would skew our test results. use your browsers developer tools to get the embedded URL and use that one for testing.

List Page

https://demo.mythemeshop.com/schema-lite/category/business/

Detail Page

https://demo.mythemeshop.com/schema-lite/lorem-ipsum-dolor-sit-amet-consectetur-adipisicing-elit/


### Theme #2
Demo URL: https://preview.themeforest.net/item/aspen-wordpress-blog-theme/full_screen_preview/22830235

Test URL: https://demos.shapingrain.com/aspen1/

List Page

https://demos.shapingrain.com/aspen1/category/lifestyle/

Detail Page

https://demos.shapingrain.com/aspen1/2018/09/29/in-search-of-the-perfect-coffee-in-downtown-manhattan/

<style>
table {font-size: 80%;}
th {text-align: left;}
th + td {text-align: right;}
.u-right, .u-passed, .u-goodEnough, .u-failed {text-align: right;}
.u-passed {color: green;}
.u-goodEnough {color: orange;}
.u-failed {color: red;}
</style>

<h4>Google Page Speed Insights</h4>
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
      <td colspan="2"><img src="i/lp-1-psi.jpg" alt=""></td>
      <td colspan="2"><img src="i/lp-2-psi.jpg" alt=""></td>
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
      <td colspan="2"><img src="i/dp-1-psi.jpg" alt=""></td>
      <td colspan="2"><img src="i/dp-2-psi.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<h4>webpagetest.org</h4>
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
      <td colspan="2"><img src="i/lp-1-wpt.jpg" alt=""></td>
      <td colspan="2"><img src="i/lp-2-wpt.jpg" alt=""></td>
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
      <td colspan="2"><img src="i/dp-1-wpt.jpg" alt=""></td>
      <td colspan="2"><img src="i/dp-2-wpt.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<h4>JS on/off</h4>
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
      <td colspan="2"><img src="i/lp-1-js-off.jpg" alt=""></td>
      <td colspan="2"><img src="i/lp-2-js-off.jpg" alt=""></td>
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
      <td colspan="2"><img src="i/dp-1-js-off.jpg" alt=""></td>
      <td colspan="2"><img src="i/dp-2-js-off.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

<h4>Google Mobile Friendly Test</h4>
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
      <td colspan="2"><img src="i/lp-1-mft.jpg" alt=""></td>
      <td colspan="2"><img src="i/lp-2-mft.jpg" alt=""></td>
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
      <td colspan="2"><img src="i/dp-1-mft.jpg" alt=""></td>
      <td colspan="2"><img src="i/dp-2-mft.jpg" alt=""></td>
    </tr>
  </tbody>
</table>

