# WASI demo
Perform file copy
https://github.com/bytecodealliance/wasmtime/blob/main/docs/WASI-tutorial.md

## Prerequisite
- Install Rust https://www.rust-lang.org/tools/install
- Install wasmtime https://docs.wasmtime.dev/cli-install.html

## Steps
1. Add wasm32-wasi toolchain
```
rustup target add wasm32-wasi
```

2. Build
```
cargo build --target wasm32-wasi
```

3. Execute
```
# This will fail because of sandboxed capability
wasmtime target/wasm32-wasi/debug/wasi-demo.wasm test.txt dest.txt

wasmtime --dir=. target/wasm32-wasi/debug/wasi-demo.wasm test.txt dest.txt
```
