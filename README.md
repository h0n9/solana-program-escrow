# solana-program-escrow

## Program Flow
1. Someone calls the entrypoint
1. The entrypoint forwards the arguments to the processor
1. The processor asks `instruction.rs` to decode the instruction_data argument
   from the entrypoint function.
1. Using the decoded data, the processor will now decide which processing
   function to use to process the request.
1. The processor may use `state.rs` to encode state into or decode the state of
   an account which has been passed into the entrypoint.

### Environment Setup
1. Install Rust from https://rustup.rs/
2. Install Solana v1.6.2 or later from
   https://docs.solana.com/cli/install-solana-cli-tools#use-solanas-install-tool

### Build and test for program compiled natively
```
$ cargo build
$ cargo test
```

### Build and test the program compiled for BPF
```
$ cargo build-bpf
$ cargo test-bpf
```
