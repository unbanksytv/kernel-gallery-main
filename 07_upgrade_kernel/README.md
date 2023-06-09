# Example: Upgrade Kernel

## Running the example

To run the kernel locally, compile the kernel to WASM with Cargo:
<!-- $MDX skip -->
```sh
$ cargo build --release --target wasm32-unknown-unknown
```

Then you can execute the kernel against the provided inputs and commands:
```sh
$ wasm-strip ../target/wasm32-unknown-unknown/release/debug_kernel.wasm -o stripped_debug_kernel.wasm
$ ../target/release/upgrade-client get-reveal-installer \
> --kernel stripped_debug_kernel.wasm \
> -P ./preimage
Root hash: 00CBAF14DF8A6BB559040E5E7EE6853AD7B0DA69DC3C85BE22646F58D802498BDE
$ octez-smart-rollup-wasm-debugger \
> ../target/wasm32-unknown-unknown/release/upgrade_kernel.wasm \
> --inputs ./inputs.json \
> --commands ./commands.json
Loaded 0 inputs at level 0
Hello from the upgrade kernel! I haven't upgraded yet.
Evaluation took 566213 ticks so far
Status: Waiting for reveal:  ˯ߊk�Y^~�:װ�i�<��"doX�I��
Internal_status: Eval
Evaluation took 13382 ticks so far
Status: Waiting for reveal:  F��+�å$�P
Internal_status: Eval
Evaluation took 350193 ticks so far
Status: Waiting for reveal:  JC쌈��ST�����0�>�.�����d�X
Internal_status: Eval
Evaluation took 350193 ticks so far
Status: Waiting for reveal:  p����o�4���ey��3�I��p���z�)��
Internal_status: Eval
Evaluation took 350193 ticks so far
Status: Waiting for reveal:  ?L?�3�|`0���9 0 6:Z.d��fc
Internal_status: Eval
Evaluation took 350193 ticks so far
Status: Waiting for reveal:  �̱ �ӭ��s��I�O����ϧ�h9&va
Internal_status: Eval
Evaluation took 350193 ticks so far
Status: Waiting for reveal:  ؏��
Internal_status: Eval
Evaluation took 350193 ticks so far
Status: Waiting for reveal:  vS��|�u8s�
�E�������p �7�
Internal_status: Eval
Evaluation took 350193 ticks so far
Status: Waiting for reveal:  ~����[?N�sUD�V�]��(G�j{��
Internal_status: Eval
Evaluation took 325809 ticks so far
Status: Evaluating
Internal_status: Evaluation succeeded
Hello from kernel!
Evaluation took 10996866192 ticks so far
Status: Evaluating
Internal_status: Evaluation succeeded
```
