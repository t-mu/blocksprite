# blocksprite

A character-map sprite editor for the web. Users draw pixel sprites on
a grid where each cell holds an ASCII character mapped to a color via
a palette — producing compact string arrays like
`["__kk__", "_kRk_", ...]` that round-trip via import.

> **Status:** under active construction. See
> [`design_handoff_blocksprite/`](./design_handoff_blocksprite/) for
> the full intended feature set.

Live: https://t-mu.github.io/blocksprite

## Getting started

Requirements: Node 24 + pnpm.

```sh
pnpm install
pnpm dev
```

Then open http://localhost:5173.

## License

ISC
