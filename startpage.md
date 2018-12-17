[Home](readme.md)

# Startpage

The startpage is a targeted page for 

* the brand of the webproperty
* one competitive phrase

The startpage is a *value hub*, and 

 * links to the most important targed pages of the webproperty 
 * to a random selection of targeted pages
 * the newest / latest updated targeted pages

## URL

The startpage must be in the root of the domain. I.e.: `https://www.example.org/`

The startpage does not redirect away from the root. I.e. 

 * no redirect from `https://www.example.org/` to `https://www.example.org/en/`
 * no redirect from `https://www.example.org/` to `https://www.example.org/welcome.html`
 * or similar 

The canonical of the startpage points to itself. I.e:: `https://www.example.org/` has the canonical `<link rel="canonical" href="https://www.example.com/" />`. If any alternate URLs for the startpage exist, they also point the canonical to the root of the domain. I.e.: `https://www.example.org/` has the canonical `<link rel="canonical" href="https://www.example.com/" />` 

## Targeting

### SEO Title
`<title>%brand% - %competitive phrase%</title>`

I.e.: <title>Example - Buy Example online</title>

### Meta Description

The meta description should fulfill common meta description best practices similar to other targeted pages.

### H1

An H1 - a biggest textual indicator of what the page is about about visible above fold - is *optional but recommended* on the startpage. In general it should be the brand or the brand and the company claim. I.e.: 

* `<h1>Example</h1>`
* `<h1>Example: The best examples on the internet</h1>`

## Content

SEO has not requirements for the content on the startpage. Structured textul content is recommended but optional.

## Interlinking

The startpage is a value hub. As a minimum we recommend: 

 * 10 links to random targeted pages
 * 10 links to most important (editorial selected) targeted pages.  
 * 10 links to newest / latest updated targeted pages.

These links must not be placed in the footer, but in a section (which can be below fold) that is still clickable for the user. I.e. with section headlines like: "Explore Example.com", "Discover Example.com", "Top Pages", "New", "Latest Update", ...

## Distribution

The startpage might not be listed in a sitemap.xml. 

## Quality Assurance

The startpage should pass the 4 SEO tests "good enough"

* Page Speed Insights: \~80 Points and correctly rendered screenshot
* Mobile Friendly Test: Green Rating and a correctly rendered screenshot
* JavaScript Turned Off:
	* Textual content should show up with JS turned off. 
	* Visible links should be clickable. 
* Fetch as GoogleBot: Fetch as GoogleBot (Mobile & Desktop) in Google Search Console should be correctly rendered and no medium or high ressource fetch warning should be listed.




