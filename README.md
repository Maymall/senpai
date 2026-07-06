![](res/icon.128.png) ![](res/logo.png)

# senpai (personal fork)

A personal fork of [senpai](https://github.com/delthas/senpai) — a modern
terminal IRC client by delthas. This fork exists mainly for provenance: it
tracks upstream and adds one local convenience feature for my own use. It is
**not** intended to be contributed back upstream.

For the full project — screenshots, features, install instructions, and
complete documentation — see the upstream repository:
<https://github.com/delthas/senpai> (mirror of
<https://git.sr.ht/~delthas/senpai>).

## What this fork adds

A native `/sjg` command that hands the terminal to an external, fullscreen
chat-history search tool without leaving senpai:

- `/sjg [query]` suspends the senpai TUI, runs the configured search command
  attached to the same terminal, and resumes senpai cleanly when it exits
  (the terminal is always restored, even if the child fails).
- The command is configurable via the `search-command` directive in the
  senpai config file and defaults to `sjg -t`. See `doc/senpai.5.scd` for the
  directive and `doc/senpai.1.scd` for the command.

That's the entire delta from upstream; everything else is unchanged.

## Building

```shell
make
```

Produces the `senpai` binary (built from `./cmd/senpai`). See the upstream
documentation for configuration and usage.

## Staying in sync with upstream

```shell
git fetch upstream
git rebase upstream/master   # replay this fork's commits on top of upstream
```

## License

ISC, same as upstream. See [LICENSE](LICENSE).
