# Installation

## Requirements

- Paper 26.2 or a fork of it (Purpur, Pufferfish, Folia)
- Java 25

Plain Spigot is not supported. The plugin will not start on it.

## Steps

1. Stop your server.
2. Drop the `.jar` into the `plugins/` folder.
3. Start the server.

The first start takes longer than usual and **requires an internet connection** —
see below.

## The first start needs network access

The plugin does not ship the database drivers inside its jar. Your server
downloads them from Maven Central the first time it starts, and caches them in
the server's `libraries/` folder. Later starts do not need network access.

This keeps the jar small (a few hundred KB instead of ~17 MB) and means several
PippiStudio plugins share one copy of each driver rather than carrying their own.

If your server has no outbound network access, the start will fail with an error
from Paper's library loader, before the plugin itself runs. In that case, either
allow outbound access to `repo1.maven.org` for the first start, or copy the
driver jars into the server's `libraries/` folder manually.

## First start

On the first start the plugin writes its configuration files into
`plugins/<PluginName>/`:

- `config.yml` — general settings, including the database backend
- `menu.yml` — menu layout
- `messages_en.yml`, `messages_zh_TW.yml` — message text

Stop the server, edit what you need, then start it again.

## Database

The default is SQLite, which needs no setup — the plugin creates a file inside
its own folder.

To use MySQL instead, set `database.type` to `mysql` in `config.yml` and fill in
the connection details. The database and the user must already exist; the plugin
creates its own tables but does not create the database.

## Updating

Replace the jar and restart. **Your configuration files are never modified by an
update.** If a new version adds options, they are listed in the server console
on startup and the plugin uses their default values until you add them yourself.

To see the full set of options for the version you are running:

```
/<plugin> config dump
```

That writes `config-latest.yml` next to your own file, so you can compare the
two. Your own file is left untouched.

## Getting help

Run `/<plugin> debug` and include the output when you open an issue. Database
passwords are masked in that output.
