[![embed-wasm on crates.io](https://img.shields.io/crates/v/embed-wasm)](https://crates.io/crates/embed-wasm) [![Documentation (latest release)](https://docs.rs/embed-wasm/badge.svg)](https://docs.rs/embed-wasm/) [![Documentation (master)](https://img.shields.io/badge/docs-master-brightgreen)](https://inanna-malick.github.io/embed-wasm/embed-wasm/)[![License](https://img.shields.io/badge/license-MIT-green.svg)](../LICENSE)[![CircleCI status](https://circleci.com/gh/inanna-malick/embed-wasm.svg?style=svg)](https://app.circleci.com/pipelines/github/inanna-malick/embed-wasm)


Library designed to allow for embedding static content generated by building rust wasm code in native rust workspaces. This allows for projects with some properties that I think are neat:

- wasm and native code in the same workspace, sharing common code including types
- embedding wasm build output in native binaries, allowing for easily-distributable apps serving dynamic frontends
- for example, a [process info visualizer](https://github.com/inanna-malick/wasm-svg-process-watcher) that renders process info using SVG and uses onclick handlers to provide for rich interactivity.

If you want to clone something so you can get started prototyping, here's an [example project](https://github.com/inanna-malick/embed-wasm-example) with a rust webserver (warp) serving a rust frontend (yew).

NOTE: this crate currently requires rust nightly due to a bug fix for a stable regression - no experimental features are used.

TODO:
- support wasm build methods other than cargo-web (doesn't seem to be under active development)
- FIXED: use phf instead of lazy_static after https://github.com/rust-lang/rust/issues/70584 is resolved 
- mark as non-nightly after the fix to that issue hits stable
