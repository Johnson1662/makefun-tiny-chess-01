# tiny-chess-01 entry

A Python chess engine for the make.fun `tiny-chess-01` bounty.

`main.py` is the submitted entrypoint. It is the packed form of the readable
source kept in `engine/engine.py`, produced with the kit's own packer:

```
node ../tiny-chess-01-kit/cli/makefun.mjs compress engine/engine.py --out main.py
```

The engine talks to the competition environment over HTTP only, uses the Python
standard library alone, and searches with a fixed node budget (so its play is
deterministic and does not depend on a clock).

## Layout

- `main.py` — packed entrypoint (standard library decompressor header plus the payload)
- `engine/` — readable source of the same program, not part of the packed entrypoint
- `LICENSE` — MIT

## License

MIT. See `LICENSE`.
