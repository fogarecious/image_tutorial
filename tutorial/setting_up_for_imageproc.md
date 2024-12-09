# Setting Up For *imageproc*

In the project directory, we add [*imageproc*](https://github.com/image-rs/imageproc) to the project.

```sh
cargo add imageproc
```

The dependencies in `Cargo.toml` file should look like this:

```toml
[dependencies]
imageproc = "0.25.0"
```

If we only add [*imageproc*](https://github.com/image-rs/imageproc) without adding [*image*](https://github.com/image-rs/image), we can precede `imageproc::` when we use [*image*](https://github.com/image-rs/image) functions.

```rust
let img = imageproc::image::open("my_image.jpg").unwrap();
```

:arrow_right:  Next: [Drawing Lines](./drawing_lines.md)

:blue_book: Back: [Table of contents](./../README.md)
