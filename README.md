# FLETCHER

**Replayable AI harness event and context-control contracts.**

FLETCHER records user turns, source reads, edits, validation obligations,
checkpoints, context deltas, and context operations as typed events. Those
events can be replayed and handed to
[LATTICE](https://github.com/giodl73-repo/LATTICE) for deterministic context
closure and receipt generation.

This public edition contains the product-neutral event model, deterministic
fixtures, and a small CLI. It does not contain private provider sessions,
customer data, funding material, or organization-specific integrations.

## Quick start

```powershell
cargo run -p fletcher-cli -- status
cargo run -p fletcher-cli -- replay
```

## Crates

| Crate | Role |
|---|---|
| `fletcher-core` | Typed harness events, deltas, checkpoints, handoff records, and deterministic fixtures. |
| `fletcher-cli` | Minimal public status and replay front door. |

## Design principles

- Capture durable events rather than treating raw chat logs as truth.
- Keep provider-specific adapters outside the core event model.
- Make validation obligations and unresolved frontiers explicit.
- Preserve enough information for deterministic replay and audit.
- Let LATTICE own semantic closure; FLETCHER owns harness capture and projection.

## Development

```powershell
cargo fmt --all -- --check
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace
```

## Status

This is an early public core extracted from a larger incubation codebase.
Provider adapters and live-session capture are intentionally out of scope for
the first public release.

## License

MIT. See [`LICENSE`](LICENSE).
