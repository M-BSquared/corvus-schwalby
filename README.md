# Schwalby for Corvus GCS

A plugin for [Corvus GCS](https://github.com/M-BSquared/CorvusGCS), the
offline ground control station for PX4 and ArduPilot.

One press buttons that start programs on this computer or over SSH, with
colours, an order you drag, and tools for an AI client that you allow one by
one.

Install it in Corvus GCS under Settings, Plugins. The full description is in
the [Corvus guide](https://m-bsquared.github.io/CorvusGCS/guide/plugins.html#schwalby).

## What it is

A Rust crate (`corvus_plugin_schwalby`) built on `corvus_api`, the plugin API of Corvus GCS, and
published as a shared library from this repository.

- `src/model.rs`: the rules, held to what the web plugin answered.
- `src/companion.rs`: the runs.
- `src/mcp.rs`: the tools for an AI client.
- `src/lib.rs`, `src/view.rs`: the plugin and what is drawn.
- `lang/`: German, French and the dialect file.

## Change it

Corvus GCS carries this repository as a submodule at `plugins/schwalby`, and the
crate is a member of its workspace:

```bash
git clone --recurse-submodules https://github.com/M-BSquared/CorvusGCS.git
cd CorvusGCS
./run.sh
```

Settings, Plugins then offers the copy built there. A dependency must be one
that `Cargo.lock` of Corvus GCS already holds.

## Publish it

Commit and push to `main`. The workflow tests the plugin, builds it for the
newest published Corvus GCS on Linux, macOS and Windows, lets that program load
it, and attaches it to the release `corvus-<version>` of this repository, where
Corvus GCS of that version finds it. A new version of Corvus GCS gets its build
within hours.

## Tests

From the Corvus checkout:

```bash
cargo test -p corvus_plugin_schwalby
```

## Licence

Sustainable Use License, see [LICENSE.md](LICENSE.md). Copyright (c) 2026
Maximilian Böck.
