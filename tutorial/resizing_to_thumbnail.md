# Resizing To Thumbnail

For scaling down an image more quickly, we can use [thumbnail](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.thumbnail).
The method [thumbnail](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.thumbnail) works in a way similar to [resize](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.resize), yet it runs faster.

```rust
fn main() {
    let img = image::open("my_image.jpg").unwrap();

    let img2 = img.thumbnail(100, 100);
    img2.save("thumbnail.jpg").unwrap();
}
```

Original image:

![my_image](./image/my_image.jpg)

thumbnail.jpg:

![thumbnail](./image/thumbnail.jpg)

There is also a method [thumbnail_exact](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.thumbnail_exact), which is the corresponding method of [resize_exact](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.resize_exact).

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
