# Drawing Texts

To draw a text on our image, we need an additional crate, [ab_glyph](https://docs.rs/ab_glyph/latest/ab_glyph/).

```sh
cargo add ab_glyph
```

The dependencies in `Cargo.toml` should look like this:

```toml
[dependencies]
ab_glyph = "0.2.29"
imageproc = "0.25.0"
```

To use the crate, we need an `otf` font file.
In the following example, we use `FogSans.otf` that can be downloaded from [this website](https://font.download/search/opentype).

```rust
use ab_glyph::FontVec;
use imageproc::{drawing, image};

use std::fs;

fn main() {
    let mut buf = image::ImageBuffer::new(100, 100);
    
    let font_data = fs::read("FogSans.otf").unwrap();
    let font = FontVec::try_from_vec(font_data).unwrap();

    drawing::draw_text_mut(
        &mut buf,
        image::Rgb::from([128u8, 255u8, 64u8]),
        10,
        34,
        24.,
        &font,
        "Draw Text",
    );

    buf.save("text.png").unwrap();
}
```

We first read the font data from the file `FogSans.otf`.
Then we transform the data to [FontVec](https://docs.rs/ab_glyph/latest/ab_glyph/struct.FontVec.html) by [FontVec::try_from_vec](https://docs.rs/ab_glyph/latest/ab_glyph/struct.FontVec.html#method.try_from_vec).
Finally, we use [draw_text_mut](https://docs.rs/imageproc/latest/imageproc/drawing/fn.draw_text_mut.html) to draw a string `Draw Text` with font size `24` at location `(10, 34)`.

text.png:

![text](./image/text.png)

Additionally, we can use [text_size](https://docs.rs/imageproc/latest/imageproc/drawing/fn.text_size.html) to get the width and height of the drawn text.

```rust
let size = drawing::text_size(24., &font, "Draw Text");
println!("{:?}", size);
```

Output:

```text
(80, 13)
```

To draw on a copied image, we can use [draw_text](https://docs.rs/imageproc/latest/imageproc/drawing/fn.draw_text.html).

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
