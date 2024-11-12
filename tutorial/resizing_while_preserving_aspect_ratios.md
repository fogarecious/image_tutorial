# Resizing While Preserving Aspect Ratios

The library provides a few methods for resizing images.
To resize an image while the aspect ratio is preserved, we can use [resize](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.resize).

```rust
use image::imageops::FilterType;

fn main() {
    let img = image::open("my_image.jpg").unwrap();
    
    let img2 = img.resize(100, 100, FilterType::Triangle);
    img2.save("resize.jpg").unwrap();
}
```

Original image:

![my_image](./image/my_image.jpg)

resize.jpg:

![resize](./image/resize.jpg)

Although we specify a square as the new image size, the method adjusts the width and height automatically to a suitable size.

In addition to [FilterType::Triangle](https://docs.rs/image/latest/image/imageops/enum.FilterType.html#variant.Triangle), there are five filters.
Readers interested in the filters may refer to [the document](https://docs.rs/image/latest/image/imageops/enum.FilterType.html) for their effects.

The example scales down the image.
But one could scale up an image to make it bigger.

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
