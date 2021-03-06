[![crates.io](https://img.shields.io/crates/v/typenum.svg)](https://crates.io/crates/typenum)
[![Build Status](https://travis-ci.org/paholg/typenum.svg?branch=master)](https://travis-ci.org/paholg/typenum)

Typenum
=====

Typenum is a Rust library for type-level numbers evaluated at compile time. It currently
supports bits, unsigned integers, and signed integers.

Typenum depends only on libcore, and so is suitable for use on any platform!

For the full documentation, go [here](http://paholg.com/typenum).

### Importing

While `typenum` is divided into several modules, they are all re-exported through the crate root,
so you can import anything contained herein with `use typenum::whatever;`, ignoring the
crate structure.

You may also find it useful to treat the `consts` module as a prelude, perfoming a glob import.

### Example

Here is a trivial example of `typenum`'s use:

```rust
use typenum::{Sum, Exp, Integer, N2, P3, P4};

type X = Sum<P3, P4>;
assert_eq!(<X as Integer>::to_i32(), 7);

type Y = Exp<N2, P3>;
assert_eq!(<Y as Integer>::to_i32(), -8);
```

For a non-trivial example of its use, see one of the crates that depends on it. The full
list is [here](https://crates.io/crates/typenum/reverse_dependencies). Of note are
[dimensioned](https://crates.io/crates/dimensioned/) which does compile-time type
checking for arbitrary unit systems and
[generic-array](https://crates.io/crates/generic-array/) which provides arrays whose
length you can generically refer to.

