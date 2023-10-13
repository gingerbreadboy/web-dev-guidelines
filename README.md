# Web Development Guidelines

## Table of contents

- [Web Development Guidelines](#web-development-guidelines)
  - [Table of contents](#table-of-contents)
- [Metrics URL (PageSpeed Insights)](#metrics-url-pagespeed-insights)
  - [Project Information](#project-information)
  - [Performance](#performance)
    - [Serve images in next-gen formats](#serve-images-in-next-gen-formats)
    - [Efficiently encode images](#efficiently-encode-images)
    - [Avoid an excessive DOM size](#avoid-an-excessive-dom-size)
    - [Defer offscreen images](#defer-offscreen-images)
    - [Problems that can be solved by WP Rocket](#problems-that-can-be-solved-by-wp-rocket)
    - [Reduce unused JavaScript](#reduce-unused-javascript)
    - [Image elements do not have explicit width and height](#image-elements-do-not-have-explicit-width-and-height)
    - [eliminate render blocking images](#eliminate-render-blocking-images)
  - [Accesibility, Best Practices](#accesibility-best-practices)
    - [Browser errors were logged to the console](#browser-errors-were-logged-to-the-console)
    - [Lists do not contain only `<li>` elements and script supporting elements](#lists-do-not-contain-only-li-elements-and-script-supporting-elements)
    - [Youtube embed unused (site slow because of youtube embed)](#youtube-embed-unused-site-slow-because-of-youtube-embed)
  - [SEO](#seo)
    - [Links are not crawlable](#links-are-not-crawlable)
    - [Links do not have a discernible name](#links-do-not-have-a-discernible-name)
    - [`<meta name="viewport">` tag with width or initial-scale](#meta-nameviewport-tag-with-width-or-initial-scale)
    - [Document doesn't use legible font sizes](#document-doesnt-use-legible-font-sizes)

# Metrics URL (PageSpeed Insights)
__[PageSpeed Insights](https://pagespeed.web.dev/)__

## Project Information
This repository is created to guide developers for creating cleaner, faster and optimized websites. Feel free to add items on this list.

## Performance

### Serve images in next-gen formats
_Image formats like WebP and AVIF often provide better compression than PNG or JPEG, which means faster downloads and less data consumption._
__images should be converted to either .svg type or .webp type, as these types of images provide less data consumption and is easier to load.__


codes for developers:

___for .WEBPs___
```javascript
<picture>
    <source srcset="" loading=“lazy” type="image/webp">
    <img src="" loading=“lazy” alt="">
</picture>
```

___for .SVGs___
```javascript
<picture>
    <source type="image/svg+xml" loading="lazy" srcset="">
    <img src="" loading="lazy" alt="">
</picture>
```

### Efficiently encode images
_Optimized images load faster and consume less cellular data._
compression of images is a vital practice for developing image-heavy sites. __You can either use a plugin or a third-party image compressor to accomplish this.__

__Samples of Image Compression Softwares__

1. [Compressor.io](https://compressor.io)
2. [Pixelled](https://pixelied.com/convert/png-converter/png-to-webp) _great tool for conversion! (you can use this for next-gen formats item)_

___Related problems:___

1. Avoids enormous network payloads


### Avoid an excessive DOM size
_excessive DOM size means that too many nodes and elements exist in your site, mostly caused by poor coding and deeply nested elements._
__this can result to slower page load times and leading to low page speed scores. You can prevent this problem by lessening the elements you use on initial coding and avoiding deeply nested elements causing bloated HTML.__

### Defer offscreen images
_Consider lazy-loading offscreen and hidden images after all critical resources have finished loading to lower time to interactive._
__use `loading="lazy"` on image elements to load images and to delay initialization of resources.__

### Problems that can be solved by WP Rocket
_problems stated below can be fixed by WP Rocket Plugin on WordPress_
1. Minify CSS
1. Minify JavaScript

### Reduce unused JavaScript
remove unused javaScript. for this item, there's nothing you can do since most of the time, this problem is caused by the GTM tags.

___Related Problems:___

1. Reduce the impact of third-party code

### Image elements do not have explicit width and height

Properly add width and height attributes to images throughout the website. you can add `width` and `height` attributes on `<img>` tags. 
Example:

`<img src="assets/img/photo.jpg" alt="image name" width="230" height="100">`

Check [caniuse.com](https://caniuse.com/mdn-css_properties_aspect-ratio) to know the browsers currently supporting the attribute.

### eliminate render blocking images

___for CSS:___
format your CSS link anchor tag with this format:
``` javascript
    <link rel="preload" 
          href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;600&display=swap" 
          as="style" 
          onload="this.onload=null;this.rel='stylesheet'" 
    />
```


## Accesibility, Best Practices
this part of the page speed insights usually has high scores compared to Performance and SEO, so we will only note important elements to fix.

___Note for designers:___

for the problem __Background and foreground colors do not have a sufficient contrast ratio.__, Some people with low vision experience low contrast, meaning that there aren't very many bright or dark areas. Everything tends to appear about the same brightness, which makes it hard to distinguish outlines, borders, edges, and details. Text that is too close in luminance (brightness) to the background can be hard to read. citation from [Study reference on contrast](https://dequeuniversity.com/rules/axe/4.7/color-contrast).

### Browser errors were logged to the console
ensure no javaScript functions shown on the browser console. Also, make sure console logging functions (such as `console.log()`) are removed before releasing the site since these functions are for testing.

### Lists do not contain only `<li>` elements and script supporting elements
for this one, avoid inserting elements inside `<ul>` or `<ol>` other than `<li>`. developers tend to add formatting elements such as `<br>` inside of list-type anchor tags. if this problem is encountered (`<li>` tags seems to behave and position themselves side by side), set `<li>` attribute to `display: block;` to occupy remaining spaces between.

### Youtube embed unused (site slow because of youtube embed)
YouTube IFrame is usually slowing down the site speed, so customizing the attributes of the IFrame will remove the errors on page speed insights.
[Youtube iFrame Generator](https://tube.rvere.com/)

## SEO
These checks ensure that your page is following basic search engine optimization advice.

### Links are not crawlable
Search engines may use href attributes on links to crawl websites. Ensure that the href attribute of anchor elements links to an appropriate destination, so more pages of the site can be discovered. ___avoid `<a href="">` without links as Google metrics crawl most of the link tags of the site. you can use `cursor: pointer;` css attribute to provide clickable appearance for non-redirecting buttons___

### Links do not have a discernible name
If images are used inside an `<a>` tag and text isn't presented, use `aria-label` tag to specify the purpose of the link.

### `<meta name="viewport">` tag with width or initial-scale
essential for browsers to read your media queries. Please include this at all times.

### Document doesn't use legible font sizes
___Note for designers:___
avoid using font sizes smmaller than 12px if possible, as users needs to pinch the screen to zoom the screen on mobile which causes poor UX. 60% of the pages' texts should have a font size of 12px and above.


___Feel free to add items here.___