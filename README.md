# Web Development Guidelines

## Table of contents

- [Web Development Guidelines](#web-development-guidelines)
  - [Table of contents](#table-of-contents)
  - [Project Information](#project-information)
  - [Performance](#performance)
    - [Serve images in next-gen formats](#serve-images-in-next-gen-formats)
    - [Efficiently encode images](#efficiently-encode-images)
    - [Avoid an excessive DOM size](#avoid-an-excessive-dom-size)
    - [Defer offscreen images](#defer-offscreen-images)
    - [Problems that can be solved by WP Rocket](#problems-that-can-be-solved-by-wp-rocket)
    - [Reduce unused JavaScript](#reduce-unused-javascript)
    - [Image elements do not have explicit width and height](#image-elements-do-not-have-explicit-width-and-height)
  - [Accesibilty, Best Practices](#accesibilty-best-practices)
    - [Browser errors were logged to the console](#browser-errors-were-logged-to-the-console)
  - [SEO](#seo)
    - [Links are not crawlable](#links-are-not-crawlable)
    - [`<meta name="viewport">` tag with width or initial-scale](#meta-nameviewport-tag-with-width-or-initial-scale)
    - [Document uses legible font sizes](#document-uses-legible-font-sizes)




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

Properly add width and height attributes to images throughout the website. if not applicable, you can use `aspect-ratio:` css attribute for your images. Check [caniuse.com](https://caniuse.com/mdn-css_properties_aspect-ratio) to know the browsers currently supporting the atrribute.


## Accesibilty, Best Practices
this part of the page speed insights usuually has high scores commpared to Performance and SEO, so we will only note important elements to fix.

___Note for designers:___

for the problem __Background and foreground colors do not have a sufficient contrast ratio.__, Some people with low vision experience low contrast, meaning that there aren't very many bright or dark areas. Everything tends to appear about the same brightness, which makes it hard to distinguish outlines, borders, edges, and details. Text that is too close in luminance (brightness) to the background can be hard to read. citation from [Study reference on contrast](https://dequeuniversity.com/rules/axe/4.7/color-contrast).

### Browser errors were logged to the console
ensure no javaScript functions shown on the browser console. Also, make sure console logging functions (such as `console.log()`) are removed before releasing the site since these functions are for testing.

## SEO
These checks ensure that your page is following basic search engine optimization advice.

### Links are not crawlable
Search engines may use href attributes on links to crawl websites. Ensure that the href attribute of anchor elements links to an appropriate destination, so more pages of the site can be discovered. ___avoid `<a href="">` without links as Google metrics crawl most of the link tags of the site. you can use `cursor: pointer;` css attribute to provide clickable appearance for non-redirecting buttons___

### `<meta name="viewport">` tag with width or initial-scale
essential for browsers to read your media queries. Please include this at all times.

### Document uses legible font sizes
___Note for designers:___
avoid using font sizes smmaller than 12px if possible, as users needs to pinch the screen to zoom the screen on mobile which causes poor UX.