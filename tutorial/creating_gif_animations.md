# Creating GIF Animations

In addition to [JpegEncoder](https://docs.rs/image/latest/image/codecs/jpeg/struct.JpegEncoder.html), there are other encoders.
For example, [GifEncoder](https://docs.rs/image/latest/image/codecs/gif/struct.GifEncoder.html) helps us create GIF animations.

In the following example, we use `resize.jpg` and [huerotate](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.huerotate) to create four images.
Then we combine these images and create a GIF animation.

To create a GIF animation, we need to put each image into a [Frame](https://docs.rs/image/latest/image/struct.Frame.html).

```rust
let frame = Frame::from_parts(img.into(), 0, 0, delay);
```

where `delay` controls how long the frame will last.

The complete code is presented below:

```rust
use image::{codecs::gif::GifEncoder, Delay, Frame};
use std::fs::File;

fn main() {
    let mut file = File::create("animation.gif").unwrap();
    let mut encoder = GifEncoder::new(&mut file);
    
    let img = image::open("resize.jpg").unwrap();
    let mut frames = vec![];
    let delay = Delay::from_numer_denom_ms(500, 1);
    
    let frame = Frame::from_parts(img.clone().into(), 0, 0, delay.clone());
    frames.push(frame);
    
    let img_90 = img.huerotate(90);
    let frame = Frame::from_parts(img_90.into(), 0, 0, delay.clone());
    frames.push(frame);
    
    let img_180 = img.huerotate(180);
    let frame = Frame::from_parts(img_180.into(), 0, 0, delay.clone());
    frames.push(frame);
    
    let img_270 = img.huerotate(270);
    let frame = Frame::from_parts(img_270.into(), 0, 0, delay.clone());
    frames.push(frame);
    
    encoder.encode_frames(frames).unwrap();
}
```

In the example, we set all delays to `500` ms.

animation.gif:

![animation](./image/animation.gif)
(Click the image to see the animation.)

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
