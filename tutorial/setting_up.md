# Setting Up

First of all, we create a [Cargo](https://doc.rust-lang.org/cargo/index.html) project,

```sh
cargo new my_project
```

where `my_project` is the name of the project.
In the project directory, we add [*image*](https://github.com/image-rs/image) to the project.

```sh
cargo add image
```

The dependencies in `Cargo.toml` file should look like this:

```toml
[dependencies]
image = "0.25.4"
```

<!-- :arrow_right:  Next:  -->

:blue_book: Back: [Table of contents](./../README.md)
