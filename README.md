# PippiStudio Support

Issue tracker, documentation and configuration reference for PippiStudio plugins.

No source code lives here.

## Reporting a problem

Open an issue in [Issues](../../issues). The template asks for the plugin
version, your server version and a debug report. All three are needed to
diagnose anything, so please fill them in completely.

If you are not sure whether something is a bug, or you just want help with
configuration, use [Discussions](../../discussions) instead.

## Configuration reference

[`configs/`](./configs) holds the complete default configuration files for the
**latest version** of every plugin. They are synced automatically by the release
pipeline, so they always match the jar you downloaded.

This is useful when you want to:

- see which options were added by an update, by comparing file history on GitHub
- check whether a particular behaviour is configurable before buying

To view the configuration for a specific version, open that version's release
notes and follow the configuration link. Those links are pinned to a commit and
will not break. If a release's notes do not have a configuration link, its
defaults are unchanged from the previous release, so that release's link still
applies.

## Requirements

- Paper 26.2 or a fork of it (Purpur, Pufferfish, Folia)
- Java 25

Plain Spigot is not supported.

Plugins support the two most recent Minecraft drops. Older versions remain
available for download on BuiltByBit but no longer receive fixes.

The first time a plugin starts, the server downloads its database driver from
Maven Central, so that first boot needs outbound network access. Later
restarts do not need it. If you run a server on a closed network, allow this
download before the plugin's first start, regardless of whether you end up
using SQLite or MySQL storage.

## Documentation

Installation guides, per-option configuration reference and frequently asked
questions are in the [Wiki](../../wiki).
