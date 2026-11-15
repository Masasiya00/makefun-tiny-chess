# tiny-chess-01

A 4KB Python chess engine for make.fun tiny-chess-01.

`main.py` is the whole engine (3,472 bytes): a packed (lzma) alpha-beta
search with quiescence, a transposition table with bound types, and a
piece-square evaluation. It plays the house gauntlet through the env
over HTTP, to a fixed node budget (100,000 nodes/move) — deterministic,
no wall clock, no model calls.

Practice trial-0 (local, manual env+scorer): Elo 1279 (2 wins, 2 draws,
2 losses), above the 1154 floor.

## Files

- `main.py` — the engine (lzma-packed; unpacks and execs itself).
- `README.md` — this file.
- `LICENSE` — MIT.

## The size rule

- `main.py` ≤ 4,096 bytes as committed (this one: 3,472).
- Python 3.13, standard library only. Reads/imports/execs no other file.
- Whole repo ≤ 8,192 bytes, no file over 4,096.
