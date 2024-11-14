# Resizing To Fill A Bound

Another way to resize an image to a specified size is to use [resize_to_fill](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.resize_to_fill).
The method scales the image (while preserving the aspect ratio) to fill the specified size and then crops the additional part.

```rust
use image::imageops::FilterType;

fn main() {
    let img = image::open("my_image.jpg").unwrap();
    
    let img2 = img.resize_to_fill(100, 100, FilterType::Triangle);
    img2.save("resize_to_fill.jpg").unwrap();
}
```

Original image:

![my_image](./image/my_image.jpg)

resize_to_fill.jpg:

![resize_to_fill](./image/resize_to_fill.jpg)

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
