# lib-ffi

`ffi` — FFI declarations for handl FFI: `Errno` and the call surface
(`ffi.call` descriptor vocabulary).

## Layout

| path | role |
| --- | --- |
| `src/ffi.hnl` | the declarations |
| `pkg.hnl` | manifest — dep `type` (`branch:main`), `modules: ["ffi"]` |
| `scripts/hnl-gate.sh` | `.hnl` gate |
| `workflows/gate.yaml` | CI — shared `handl-gates` campaign |

## Contract

- Declaration module consumed by every `ffi.call` backend
  (`cli-c`, `fetch-c`, `compress-*-c`, `json-c`, …) — keep the
  descriptor vocabulary stable; backends codegen or hand-write against
  it.
- Single `.hnl` file; no Rust crate in this repo.

## Verification

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
