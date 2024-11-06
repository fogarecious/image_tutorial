# Color Types

The color type of an image describes the color channels (such as red, green, blue, gray and alpha) used by the image and the number of bits for each channel.
We can use [color](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.color) to obtain this information.

```rust
fn main() {
    let img = image::open("my_image.jpg").unwrap();
    println!("Color type: {:?}", img.color());
}
```

Output:

```text
Color type: Rgb8
```

`Rgb8` means each color in the image is consisted of red, blue and green channels and each channel has 8 bits.

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
