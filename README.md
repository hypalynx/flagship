# Flagship 🔱

_Leading the way in web development._

This project is an example of how a website should be built! It
provides everything you should need to create most things on the
internet. From e-commerce sites to internal dashboards, this
flagship is prepared to take you anywhere.

## The Stack

### Base

- deno (better security, built-in/simpler toolchain!)
  - formatter
  - linter
  - typescript + jsx/tsx supported
  - build tool for both frontend + backend
- typescript (great for validating frontend components)
- [zod](https://zod.dev/) (create data schemas to test at the edge of your system)
- pino (structured logging)

### Server

- hono (simple yet powerful)
- SQLite (no cache required and good enough for most tasks) 
- @db/sqlite (FAST + supports extensions + custom functions)

### Client

- plain CSS (elements.css + custom classes per project)
- React (tried and true, Shopify uses it)
- Zustand
- Wouter
- Phosphor Icons (using sprite sheets)

### Devops

- Litestream (backup SQLite on the fly)
- Grafana and friends? (is there anything more lightweight/just
  logs analysis? what about alerts?)
- Using Deno's built in support for [OpenTelemetry](https://docs.deno.com/runtime/fundamentals/open_telemetry/)
- `k3s` for single VPS deploys with:
  - Automatic SSL via Traefik + cert-manager
  - Loki/Grafana/Tempo/Prometheus

## On CSS

Styling is generally done directly on the elements where possible
with an escape hatch `.unstyled` class to remove it in cases
where you might, for example, want an input to *not* look like an
input.

This keeps styles reusable and automatic with an option to move
them out the way when things get customised.

CSS variables are also used to allow for control of the styled
elements i.e `var(--radius)` can be used to control how rounded
the elements in your design are.
