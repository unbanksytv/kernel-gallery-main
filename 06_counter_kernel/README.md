# Example: Debug Kernel

In our second kernel, we will demonstrate how to write and read data in durable state of the rollup.

## Running the example

First, compile the kernel to WASM with Cargo:

<!-- $MDX skip -->

```sh
$ cargo build --release --target wasm32-unknown-unknown
```

Then you can execute the kernel locally against the provided inputs (empty in this example) and commands:

```sh
$ octez-smart-rollup-wasm-debugger \
> ../target/wasm32-unknown-unknown/release/debug_kernel.wasm \
> --inputs ./inputs.json \
> --commands ./commands.json
...
0000000000000005
```

Additionally, you can omit the `--commands` flag to enter a REPL mode and
explore the execution of the kernel interactively. Try it out!
