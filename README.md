# Dataleap Docs

This repository contains the end-user documentation site for Dataleap, built with Mintlify.

## Development

Install the Mintlify CLI if you do not already have it:

```bash
npm i -g mint
```

Run the local preview:

```bash
mint dev
```

Useful checks:

```bash
mint broken-links
mint validate
```

## Structure

- `docs.json` configures the site navigation and branding.
- `*.mdx` files define the docs pages.
- `images/` stores static assets used in documentation.
