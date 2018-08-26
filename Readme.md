Timebomb
========

[![Build Status](https://travis-ci.org/csherratt/timebomb.svg?branch=master)](https://travis-ci.org/csherratt/timebomb)
[![crates.io](https://meritbadge.herokuapp.com/timebomb)](https://crates.io/crates/timebomb)

This is a simple timeout mechanism for Rust that is intended for use with unit tests.

`Cargo.toml`:
```toml
[dependencies]
timebomb = "0.1.2"
```

```rust
extern crate timebomb;
use timebomb::timeout_ms;

#[test]
fn something_bad() {
	// This will timeout in 1 second if the test did not pass
	timeout_ms(|| {
		// oops infinite loop
		loop {}
	}, 1000);
}
```
