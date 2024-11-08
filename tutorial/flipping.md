# Flipping

To flip an image horizontally or vertically, we can use [fliph](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.fliph) and [flipv](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.flipv).

```rust
fn main() {
    let img = image::open("my_image.jpg").unwrap();
    
    let img_fliph = img.fliph();
    img_fliph.save("fliph.jpg").unwrap();
    
    let img_flipv = img.flipv();
    img_flipv.save("flipv.jpg").unwrap();
}
```

Original image:

![my_image](./image/my_image.jpg)

fliph.jpg:

![fliph](./image/fliph.jpg)

flipv.jpg:

![flipv](./image/flipv.jpg)

We can also use [apply_orientation](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.apply_orientation) to achieve the same results.

:arrow_right:  Next: [Rotating](./rotating.md)

:blue_book: Back: [Table of contents](./../README.md)
