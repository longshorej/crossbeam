# Crossbeam Epoch

[![Build Status](https://travis-ci.org/crossbeam-rs/crossbeam.svg?branch=master)](
https://travis-ci.org/crossbeam-rs/crossbeam)
[![License](https://img.shields.io/badge/license-MIT%2FApache--2.0-blue.svg)](
https://github.com/crossbeam-rs/crossbeam-epoch)
[![Cargo](https://img.shields.io/crates/v/crossbeam-epoch.svg)](
https://crates.io/crates/crossbeam-epoch)
[![Documentation](https://docs.rs/crossbeam-epoch/badge.svg)](
https://docs.rs/crossbeam-epoch)
[![Rust 1.26+](https://img.shields.io/badge/rust-1.26+-lightgray.svg)](
https://www.rust-lang.org)

This crate provides epoch-based garbage collection for building concurrent data structures.

When a thread removes an object from a concurrent data structure, other threads
may be still using pointers to it at the same time, so it cannot be destroyed
immediately. Epoch-based GC is an efficient mechanism for deferring destruction of
shared objects until no pointers to them can exist.

## Usage

Add this to your `Cargo.toml`:

```toml
[dependencies]
crossbeam-epoch = "0.7"
```

Next, add this to your crate:

```rust
extern crate crossbeam_epoch as epoch;
```

## Compatibility

The minimum supported Rust version is 1.26.

This crate can be used in `no_std` environments, but only on nightly Rust.

## License

Licensed under either of

 * Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.
