# Loading And Saving Images In Memory

To save an image to memory, we can use [write_to](https://docs.rs/image/latest/image/enum.DynamicImage.html#method.write_to).

```rust
img.write_to(&mut buffer, ImageFormat::Jpeg).unwrap()
```

With the method, we can specify the [ImageFormat](https://docs.rs/image/latest/image/enum.ImageFormat.html) we are going to save.
Here, the `buffer` is just a [Vec](https://doc.rust-lang.org/std/vec/struct.Vec.html) encapsulated in [Cursor](https://doc.rust-lang.org/std/io/struct.Cursor.html).

On the other hand, to load an image from memory, we can use [image::load_from_memory](https://docs.rs/image/latest/image/fn.load_from_memory.html).

```rust
load_from_memory(buffer.get_ref()).unwrap();
```

We get the reference of the [Vec](https://doc.rust-lang.org/std/vec/struct.Vec.html) in [Cursor](https://doc.rust-lang.org/std/io/struct.Cursor.html) and pass it to the function.

The complete code is shown below:

```rust
use std::io::Cursor;
use image::{load_from_memory, ImageFormat};

fn main() {
    let img = image::open("my_image.jpg").unwrap();
    
    let mut buffer = Cursor::new(vec![]);
    img.write_to(&mut buffer, ImageFormat::Jpeg).unwrap();

    let img2 = load_from_memory(buffer.get_ref()).unwrap();
    img2.save("saved_image.jpg").unwrap();
}
```

my_image.jpg:
![my_image](./image/my_image.jpg)

saved_image.jpg:
![saved_image](./image/saved_image.jpg)

:arrow_right:  Next: [Width And Height](./width_and_height.md)

:blue_book: Back: [Table of contents](./../README.md)
