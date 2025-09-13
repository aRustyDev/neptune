# neptune
Generate diagrams and charts from a DSL, as MDX consumable artifacts

```bash
ls --tree docs/src
󱧼 project
├── 󱧼 docs
│   ├──  book.toml
│   ├── 󱧼  book
│   │   └──  ... (ignored)
│   └── 󱧼  src
│       ├── 󱧼  ... (dirs)
│       │   └──  ... (*.md)
│       └──  SUMMARY.md
├──  README.md
└── 󱧼  src
    ├──  main.rs
    └── 󱧼  modFoo/
        ├──  foo.rs
        └──  mod.rs
```


```bash
neptune -i foo.td -o docs/book/
cat foo.td | neptune -o docs/book/
```

```toml
# neptune.toml
[config]
output_dir = "docs/book"
theme = "default"
background = "white"

[charts.fooType]
value = "bar"
```

## Env settings

- RULE: Neptune will never update the environment variables.
- RULE: Neptune is lazy by default and will default to all kinds being in one location, in the users `$HOME/.config/neptune`
- These gets set by Neptune if not set in shell environment variables.
  - `NEPTUNE_ROOT`: Path to the neptune directory. Defaults to `${XDG_CONFIG_HOME:-$HOME/.config}/neptune`.
- These overwrite `NEPTUNE_ROOT` settings if set
  - `NEPTUNE_BIN`: Path to the bin directory. Defaults to `${XDG_BIN_HOME:-$NEPTUNE_ROOT/bin}/neptune`.
  - `NEPTUNE_DATA`: Path to the data directory. Defaults to `${XDG_DATA_HOME:-$NEPTUNE_ROOT/share}/neptune`.
  - `NEPTUNE_CACHE`: Path to the cache directory. Defaults to `${XDG_CACHE_HOME:-$NEPTUNE_ROOT/cache}/neptune`.
  - `NEPTUNE_STATE`: Path to the state directory. Defaults to `${XDG_STATE_HOME:-$NEPTUNE_ROOT/state}/neptune`.
  - `NEPTUNE_CONFIG`: Path to the config directory. Defaults to `${XDG_CONFIG_HOME:-$NEPTUNE_ROOT}/neptune`.
