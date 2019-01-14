---
title: URLs Test
---

# URLs

General recommended format for targeted pages is `https://www.%domain-name%.%tld%/%namespace%/%unique-slug%`.

I.e.:

* `https://www.example.com/a/an-editorial-slug` (recommended for editorial created URLs)
* `https://www.example.com/v/123456` (recommended for automatic i.e. data import created URLs)

## URL-Rules

* URL-Rule 1: unique (1 URL == 1 resource, 1 resource == 1 URL)
* URL-Rule 2: permanent (they do not change, no dependencies to anything)
* URL-Rule 3: manageable (equals measurable, 1 logic per site section, no exceptions)
* URL-Rule 4: easily scalable logic
* URL-Rule 5: short
* URL-Rule 6: with a variation (partial) of the targeted phrase 

URL-Rule 1 is more important than 1 to 6 combined, URL-rule 2 is more important than 2 to 6 combines, … URL-Rule 5 and 6 are always a trade-of.

Systematic SEO is not possible if URL-Rule 1 & 2 are not fulfilled.

As measurbility and optimization are two sides of the same coin, the one is not possible without the other. For long term SEO URL-Rule 3 must be fulfilled. 

An URL the fulfilles URL-Rule 1 to 5 i.e.: `https://www.example./v/123456` is "good enough" and can be optimized in a scaling and systematic way. 

A truly search optimized URL must fulfill all URL-Rules.

URL-Rule Nr. 6 must never invalidate URL-Rule 1 to 5!

## Keepings URL-slugs simple

As https://www.example.com/a/an-editorial-slug is not the same URL as https://www.example.com/a/aN+editoriAl%20Slug/ (upper-lower-case issue, multiple possible word seperator issue, ending-slash-no-ending-slash issue) but on quite some server setups deliver the same content, thus violating "URL-Rule 1: unique" I recommend some "keep URL slugs simple" best practices.

An URL slug can only contain following characters

 * a to z (lowercase)
 * 0 to 9
 * - as a word sperator (no %20, no +, no _) 
 * no ending slash 
 
 Any URL-variation (i.e. uppercase URLs, wrong word seperator, ending slash for non ending slash URLs) should return HTTP 404.  See the Dead-Weight chapter for more about wrong URLs handling. 
 
## URL-Rule 1:

## URL-Rule 2:

## Don't overdo the f\*cking URLs!

## URL-Rule 3: manageable  

exception "no ending slash": this is only for our recommended URL format. If you have URLs that communicate some hierchy (as discussed not recommended) and URL that has sub-pages, sub-hierachies does have an ending slash. I.e.: 


* `https://www.example.com/traffic/` traffic sub section start page
* `https://www.example.com/traffic/bus-traffic-vienna` an editorial detail page

The reason for this is that if you want to analyze the sub-section "traffic" - in Google Search Console or Google Analytics - you can simple filter for "/traffic/". If the subsection startpage would be https://www.example.com/traffic you can not easily filter for the metrics of the the whole subsection, as a filter for "/traffic/" would not include "/traffic", but a filter for "traffic" or even "/traffic" might include false positives.

## URL-Rule 4:

## URL-Rule 5:

## URL-Rule 6: