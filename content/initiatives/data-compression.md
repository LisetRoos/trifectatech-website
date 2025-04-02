+++
title = "Data compression"
slug = "data-compression"
template = "initiatives/initiative.html"

[taxonomies]
category = ["infrastructure"]

[extra]
summary = "<p>Almost all content sent over the Internet undergoes data compression using algorithms like zlib and zstd.</p>"

funders = [
    "devolutions", 
    "prossimo", 
    "chainguard", 
    "tweedegolf", 
    "nlnetfoundation", 
    "ngi-zero-core",
    "isrg",
    "min-bzk"
]

blogposts = [
    "Translating bzip2 with c2rust",
    "zlib-rs is faster than C",
    "The fastest WASM zlib",
    "Trifecta Tech Foundation is the new home for memory safe zlib",
    "Current zlib-rs performance",
    "flate2 release v1.0.29 with new `zlib-rs` feature",
    "xz incident shows the need for structural change"
]
+++

### Building a data compression ecosystem

Compression algorithms are used in a vast number of protocols and file formats throughout all of computing. Implemented in C, these libraries encounter regular security issues despite receiving extensive industry-wide scrutiny.

Our initiative aims to create **memory-safe** implementations of compression libraries:

- **zlib**: a widely-used compression library, used primarily on the web to provide gzip compression to the text/html/js/css we send around.
- **zstd**: a modern successor to zlib, providing better compression faster. 
- **bzip2**: a file compression program that is widely deployed and supported e.g. as part of zip.
- **xz**: a compression format that provides very good compression, but is comparatively slow. Commonly used for large file downloads.

Please [get in touch with us](/support), if you are interested in financially supporting the development of memory-safe zlib, zstd or xz. We offer technical support services for organizations wanting to adopt our data compression software.

### What We've Done

For zlib, we've created an implementation based on zlib-ng, called `zlib-rs`, with a focus on maintaining excellent performance while introducing memory safety. The initial development of `zlib-rs` was started and partly funded by [Prossimo](https://www.memorysafety.org/initiative/zlib/) and [Tweede golf](https://tweedegolf.nl/en).

In April 2024, an early release of zlib-rs was [integrated in flate2](https://github.com/rust-lang/flate2-rs/releases/tag/1.0.29). In Nov 2024 an audit by [ISRG](https://www.abetterinternet.org/) was succesfully completed, and optimizations for Webassembly were included in a [new release](https://github.com/trifectatechfoundation/zlib-rs/releases).

The development of `bzip2`, the 2nd project in this initiative, started Oct 2024. Unlike in `zlib-rs` we use `c2rust` to translate the original bzip2 C code to Rust. Early releases are [available on GitHub](https://github.com/trifectatechfoundation/libbzip2-rs?tab=readme-ov-file#how-to-use-libbzip2-rs-in-your-project), and also through the [bzip2 crate](https://crates.io/crates/bzip2) we now maintain.

### What's Next

We're currently seeking funding to complete work on `zlib` and to start work on xz and zstd. 

The high level goals for the four projects are:

- provide on-par performance with C/C++ counterparts
- provide a dynamic library that is a drop-in replacement, but has compiled memory-safe rust code inside
- dramatically reduce attack surface through memory safety, improved tooling and a robust build system
- provide a pure rust implementation to rust users that integrates with the existing ecosystem

### Work plan

For per project details, see [the workplan](/initiatives/workplans/data-compression).

Please [get in touch with us](/support), if you are interested in financially supporting the development of memory-safe zlib, zstd or xz.

### Links

- [video] [Implementing zlib in Rust](https://www.youtube.com/watch?v=mvzHQdCLkOY&list=PL8Q1w7Ff68DBZZbJt3ie5MUoJV5v2HeA7&index=11)
- [zlib-rs GitHub Repository](https://github.com/trifectatechfoundation/zlib-rs/)
- [bzip2-rs GitHub Repository](https://github.com/trifectatechfoundation/bzip2-rs)
