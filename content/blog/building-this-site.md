+++
title = "Building this site with Rust"
date = "2026-06-10"
description = "A quick look at the static site generator behind this blog."
+++

A short post on the tooling behind this site.

## Why a custom generator?

There are plenty of great static site generators out there (Zola, Hugo,
Jekyll...), but I wanted something small, hackable, and written in a
language I love working with: Rust.

## The stack

- **pulldown-cmark** — CommonMark Markdown parsing
- **tera** — Jinja2-style HTML templating
- **toml** + **serde** — front matter parsing
- **chrono** — date handling and sorting for blog posts

The generator walks the `content/` directory, converts each Markdown file
to HTML, plugs it into a template, and writes the result to `dist/`. From
there, any static host can serve it.
