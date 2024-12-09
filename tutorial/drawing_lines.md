# Drawing Lines

We can draw lines on an image.
First, we create an [ImageBuffer](https://docs.rs/image/latest/image/struct.ImageBuffer.html).
For the purpose of clear demonstration, we make the image has low resolution.
Then, we use [draw_line_segment_mut](https://docs.rs/imageproc/latest/imageproc/drawing/fn.draw_line_segment_mut.html) to draw a line on the image.
The function needs the two end points of the line and the color of it.

```rust
use imageproc::{drawing, image};

fn main() {
    let mut buf = image::ImageBuffer::new(100, 100);

    drawing::draw_line_segment_mut(
        &mut buf,
        (0, 10),
        (100, 90),
        image::Rgb::from([128u8, 255u8, 64u8]),
    );
    buf.save("line.png").unwrap();
}
```

line.png:

![line](./image/line.png)

Another function to draw a line is by [draw_line_segment](https://docs.rs/imageproc/latest/imageproc/drawing/fn.draw_line_segment.html).
Instead of mutating the original image, this function creates a copy of the image and draws on the copy.

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
