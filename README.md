# lib-ffi

`ffi` — FFI decls for handl FFI (Errno, call surface); the `ffi.hnl`
interface plus a const-only Rust crate.

## Layout

```text
src/                     ffi.hnl plus the const crate
pkg.hnl                  package manifest
scripts/hnl-gate.sh      the gate
workflows/gate.yaml                    bupha entry (handl-gates)
```

## Gate

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

## License

MIT.
