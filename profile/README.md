# gql-x

A family of composable, layered libraries for building GraphQL queries from host-language values rather than templated strings.

The core idea: a small, backend-agnostic query composer at the base, and backend-flavored plugins on top of it that add the conventions specific to a given GraphQL-speaking system. Each layer is independently versioned and adoptable. Output is always plain, spec-compliant GraphQL text — `gql-x` projects produce input *for* the rest of the GraphQL ecosystem, not a replacement for any part of it.

## Current Packages

- **[composer](https://github.com/gql-x/composer)** — the base library. A general-purpose GraphQL query composer with variable hoisting, dynamic composition, and a small extension surface for plugin authors. Spiritual successor to the legacy `gql-query-builder` package, but with no shared code.

- **[plugin-defradb](https://github.com/gql-x/plugin-defradb)** — a plugin targeting [DefraDB](https://source.network/defradb), the open-source peer-to-peer document database from Source Network. Adds DefraDB's filter shapes, input shapes, aggregates, grouped aggregates, and `over`-style arguments on top of composer.

## Getting Started

If you want to build GraphQL queries against any GraphQL endpoint, start with **[composer](https://github.com/gql-x/composer)**.

If you're working with DefraDB specifically, **[plugin-defradb](https://github.com/gql-x/plugin-defradb)** is the right entry point — it bundles composer plus the DefraDB-flavored vocabulary.

## Status

Early. All packages are pre-1.0 and the extension surface is still being shaped by what current plugins need. Expect things to move.
