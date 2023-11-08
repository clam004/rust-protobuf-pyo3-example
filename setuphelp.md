## Troubleshooting

```
  Error: pyo3 requires a nightly or dev version of Rust.
  note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
error: `cargo rustc --lib --message-format=json-render-diagnostics --manifest-path Cargo.toml -v --features pyo3/extension-module --crate-type cdylib -- -C 'link-args=-undefined dynamic_lookup -Wl,-install_name,@rpath/core.cpython-311-darwin.so'` failed with code 101
```

The error message you're seeing indicates that the `pyo3` package you are trying to build requires a nightly or dev version of Rust, but your current Rust installation is not a nightly or dev version.

To resolve this issue, you can follow these steps:

1. Install a nightly or dev version of Rust:
   You can install the nightly version of Rust using Rustup, which is a tool for managing Rust installations. If you don't have Rustup installed, you can get it from the official website: https://rustup.rs/. Once you have Rustup, you can install the nightly version with the following command:

   ```bash
   rustup install nightly
   ```

2. Switch to the nightly version of Rust for your project:
   To use the nightly version of Rust for your project, navigate to your project directory and run the following command:

   ```bash
   rustup override set nightly
   ```

   This command will set the nightly version of Rust as the default for your project.

3. Rerun the `python setup.py develop` command:
   Once you have the nightly version of Rust set for your project, try running the `python setup.py develop` command again. It should work without the error.

If you encounter any issues or if you need more assistance, feel free to ask for help.