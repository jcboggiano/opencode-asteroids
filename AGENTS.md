# AGENTS.md

## Project

Single-file HTML5 canvas Asteroids clone. No package.json, dependencies, bundler, build, lint, or tests. Open `index.html` directly or run `npx serve .`.

## Structure

- `index.html` — fixed 800x600 canvas, loads `game.js` as a classic script.
- `game.js` — all game code: input, entities, state machine, update/draw, RAF loop.
- `favicon.svg`, `README.md`.

## Conventions

- `game.js` is not a module: keep it a classic script with top-level globals and classes. Do not add imports/`type="module"` without a reason.
- Canvas size lives in both `index.html` and `const W/H` in `game.js`; change both together.
- Keep UI strings and comments in Spanish, matching the existing style.
- No comments are required for new code; existing section comments are fine.

## Game internals worth knowing

- State machine: `state` is `'playing'`, `'dead'`, or `'gameover'`; `update()` branches on it.
- Asteroid `size` is inverted: `3` = large, `2` = medium, `1` = small. `RADII`, `SPEEDS`, and `POINTS` are indexed by `size`.
- Input uses `e.code` (`'Space'`, `'ArrowUp'`, ...). Edge-triggered actions must use `pressed(code)`; `keys[code]` is for held input.
- `dist()` is plain Euclidean distance; collision across wrapped screen edges is not handled.
- Loop clamps `dt` to 0.05s; keep per-frame logic in `update(dt)`/`draw()`.

## Verification

Manual browser testing only. Check movement, shooting, asteroid splitting/scoring, life loss, level transitions, and Space-to-restart after game over. There is no automated check to run.

## Docs caveat

`README.md` advertises power-ups and a "shooting star" asteroid that are not implemented in `game.js`. Treat code as source of truth unless the task is explicitly to add those features.
