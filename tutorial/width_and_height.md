# Width And Height

We can use [width](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.width), [height](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.height) and [dimensions](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.dimensions) to get the size of an image.

```rust
use image::GenericImageView;

fn main() {
    let img = image::open("my_image.jpg").unwrap();

    println!("Width: {}", img.width());
    println!("Height: {}", img.height());
    println!("Dimensions: {:?}", img.dimensions());
}
```

Output:

```text
Width: 1024
Height: 768
Dimensions: (1024, 768)
```

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
