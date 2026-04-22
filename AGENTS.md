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

## Svelte MCP

You are able to use the Svelte MCP server, where you have access to comprehensive Svelte 5 and SvelteKit documentation. Here's how to use the available tools effectively:

### Available Svelte MCP Tools:

#### 1. list-sections

Use this FIRST to discover all available documentation sections. Returns a structured list with titles, use_cases, and paths.
When asked about Svelte or SvelteKit topics, ALWAYS use this tool at the start of the chat to find relevant sections.

#### 2. get-documentation

Retrieves full documentation content for specific sections. Accepts single or multiple sections.
After calling the list-sections tool, you MUST analyze the returned documentation sections (especially the use_cases field) and then use the get-documentation tool to fetch ALL documentation sections that are relevant for the user's task.

#### 3. svelte-autofixer

Analyzes Svelte code and returns issues and suggestions.
You MUST use this tool whenever writing Svelte code before sending it to the user. Keep calling it until no issues or suggestions are returned.

#### 4. playground-link

Generates a Svelte Playground link with the provided code.
After completing the code, ask the user if they want a playground link. Only call this tool after user confirmation and NEVER if code was written to files in their project.
