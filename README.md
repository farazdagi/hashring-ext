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

- [ ] Balanced distribution of keys, using virtual nodes
- [ ] Heterogeneous nodes, using node weights
- [ ] Automatic key space delta range calculations, on node addition/removal

## License

MIT
