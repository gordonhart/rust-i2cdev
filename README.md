# Rust I2cdev

[![Build Status](https://travis-ci.org/rust-embedded/rust-i2cdev.svg?branch=master)](https://travis-ci.org/rust-embedded/rust-i2cdev)
[![Version](https://img.shields.io/crates/v/i2cdev.svg)](https://crates.io/crates/i2cdev)
[![Docs](https://docs.rs/i2cdev/badge.svg)](https://docs.rs/i2cdev)
[![License](https://img.shields.io/crates/l/i2cdev.svg)](https://github.com/rust-embedded/rust-i2cdev/blob/master/README.md#license)

The Rust `i2cdev` crate seeks to provide full access to the Linux i2cdev
driver interface in Rust without the need to wrap any C code or directly make
low-level system calls.  The documentation for the i2cdev interace can
be found in the [Linux Kernel documentation](https://www.kernel.org/doc/Documentation/i2c/dev-interface).

Device driver developers should consider building on top of the
[embedded-hal](https://crates.io/crates/embedded-hal) traits rather than
directly coupling to this library. An implementation of those generic traits for
Linux can be found in
[linux-embedded-hal](https://crates.io/crates/linux-embedded-hal) which, at
present, uses this crate as the backend for I2C.

## Example/API

The source includes an example of using the library to talk to a Wii
Nunchuck (which has an I2C interface).
[Go View the Example](https://github.com/rust-embedded/rust-i2cdev/blob/master/examples/nunchuck.rs).

The [Documentation](https://docs.rs/i2cdev) contains a quick overview of how to
get started with an I2C device.

In addition to the Read/Write traits, the following methods are
available via the [I2CDevice trait](https://rust-embedded.github.io/rust-i2cdev/i2cdev/core/trait.I2CDevice.html).

## Features

The following features are implemented and planned for the library:

- [x] Implement the Read trait
- [x] Implement the Write trait
- [x] Implement SMBus Methods
- [x] Add Tests/Example for SMBus Methods
- [x] Add sensor library for handy sensors (and examples)
- [ ] Add higher-level APIs/Macros for simplifying access to devices
      with large register sets
- [ ] Add Support for Non-SMBus ioctl methods
- [ ] Add examples for non-SMBus ioctl methods
- [ ] Unit Testing

## Cross Compiling

Most likely, the machine you are running on is not your development
machine (although it could be).  In those cases, you will need to
cross-compile.  See [this Rust cross-compilation guide](https://github.com/japaric/rust-cross)
for pointers.

## License

Licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or
  http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.

## Code of Conduct

Contribution to this crate is organized under the terms of the [Rust Code of
Conduct][CoC], the maintainer of this crate, the [Embedded Linux Team][team],
promises to intervene to uphold that code of conduct.

[CoC]: CODE_OF_CONDUCT.md
[team]: https://github.com/rust-embedded/wg#the-embedded-linux-team
