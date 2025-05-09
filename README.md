# hashring-ext

[![crates.io](https://img.shields.io/crates/d/hashring-ext.svg)](https://crates.io/crates/hashring-ext)
[![docs.rs](https://docs.rs/hashring-ext/badge.svg)](https://docs.rs/hashring-ext)
[![unsafe forbidden](https://img.shields.io/badge/unsafe-forbidden-success.svg)](https://github.com/rust-secure-code/safety-dance/)
[![dependencies](https://deps.rs/repo/github/farazdagi/hashring-ext/status.svg)](https://deps.rs/repo/github/farazdagi/hashring-ext)

Consistent hashing algorithm implementation based on the
[Consistent hashing and random trees: distributed caching protocols for relieving hot spots on the World Wide Web](https://dl.acm.org/doi/10.1145/258533.258660)
paper.

This implementation features not only the original consistent hashing algorithm, but also number of
convenient extensions, which help to manage the key space and the ring state.

## Features

- [ ] Thread-safe, using lock-free data structures
- [ ] Based on the classic consistent hashing algorithm, with a few extensions:
  - [ ] Balanced distribution of keys using virtual nodes
  - [ ] Heterogeneous cluster with weighted nodes allowed
  - [ ] Replication of keys across multiple nodes
- [ ] Automatic key space changes (what ranges to be moved between which nodes) calculations, on
  node addition/removal. Client code will have enough information to perform the actual data
  migration.

## Motivation

While there are number of implementations of consistent hashing in Rust, most of them are limited to
the most trivial use cases. This library is designed to be a more complete solution, which can be
used in virtually any context, where consistent hashing is needed.

One of the main goals of the library is to provide not only basic keys to nodes mapping, but
facilitate ring re-balancing and data migration as well. Whenever cluster topology changes, the
library will provide enough information to perform the actual data migration, so that client will
not have to worry about calculating the ranges of keys to be moved between nodes. This is especially
non-trivial when the replication factor is greater than 1, or when the cluster is heterogeneous.

## License

MIT
