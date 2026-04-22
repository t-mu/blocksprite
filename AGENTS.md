# blocksprite

A character-map sprite editor. Users draw on a grid where each cell is
an ASCII character that maps to a color via a palette. Output is a
compact string-array that can be pasted back in to round-trip.

## Conventions

- **One component per file.** No exceptions.
- **Svelte 5 runes** (`$state`, `$derived`, `$effect`) — not stores.
- **Client-only.** The root layout disables SSR and enables prerender.
  `window`, `localStorage`, `ResizeObserver` are fair game.
- **Dependencies pinned to exact versions.** Every package must be
  declared in `package.json` (no runtime CDN imports), and versions
  carry no `^` / `~` / `>=` matchers. `.npmrc` sets `save-prefix=''`
  so `pnpm add` saves exact versions by default.
- **Conventional Commits with required scope.** Commit subjects follow
  `type(scope): subject` — scope is required, not optional. Example:
  `feat(canvas): add bucket fill tool`. Types: `feat`, `fix`, `docs`,
  `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`,
  `revert`. Use `!` after the scope (or a `BREAKING CHANGE:` footer)
  for breaking changes.

## Design reference

The UI is defined in `design_handoff_blocksprite/`. Treat the HTML
prototype there as the visual source of truth — tokens, layout, and
interactions are finalized. Recreate in Svelte using the existing
`:root` custom-property token system.
