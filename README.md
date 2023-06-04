# Web Development Guidelines

## Table of contents

- [Web Development Guidelines](#web-development-guidelines)
  - [Table of contents](#table-of-contents)
    - [Project Information](#project-information)
    - [Serve images in next-gen formats](#serve-images-in-next-gen-formats)
      - [for .WEBPs](#for-webps)
      - [for .SVGs](#for-svgs)




### Project Information
This repository is created to guide developers for creating cleaner, faster and optimized websites. Feel free to add items on this list.


### Serve images in next-gen formats
Image formats like WebP and AVIF often provide better compression than PNG or JPEG, which means faster downloads and less data consumption.


#### for .WEBPs
```javascript
<picture>
    <source srcset="" loading=“lazy” type="image/webp">
    <img src="" loading=“lazy” alt="">
</picture>
```

#### for .SVGs
```javascript
<picture>
    <source type="image/svg+xml" loading="lazy" srcset="">
    <img src="" loading="lazy" alt="">
</picture>
```
