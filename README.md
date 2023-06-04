# Web Development Guidelines

## Table of contents

- [Web Development Guidelines](#web-development-guidelines)
  - [Table of contents](#table-of-contents)
    - [Project Information](#project-information)
    - [Serve images in next-gen formats](#serve-images-in-next-gen-formats)
    - [Efficiently encode images](#efficiently-encode-images)
    - [Avoid an excessive DOM size](#avoid-an-excessive-dom-size)
    - [Defer offscreen images](#defer-offscreen-images)




### Project Information
This repository is created to guide developers for creating cleaner, faster and optimized websites. Feel free to add items on this list.


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

___Problems that can also be fixed by resource compression:___

1. Avoids enormous network payloads


### Avoid an excessive DOM size
_excessive DOM size means that too many nodes and elements exist in your site, mostly caused by poor coding and deeply nested elements._
__this can result to slower page load times and leading to low page speed scores. You can prevent this problem by lessening the elements you use on initial coding and avoiding deeply nested elements causing bloated HTML.__

### Defer offscreen images
_Consider lazy-loading offscreen and hidden images after all critical resources have finished loading to lower time to interactive._
__use `loading="lazy"` on image elements to load images and to delay initialization of resources.__