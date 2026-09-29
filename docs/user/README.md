# User Guides

> Historical reference only. Do not install or use this package for new work. This repository is deprecated, unsupported, and read-only.

These guides record how `jido_command` worked at its final source commit. They do not provide a supported setup or migration path.

## What the final runtime did

- Loads markdown commands from global and local roots.
- Compiles each command into a `Jido.Action` module.
- Executes commands directly (`invoke`) or by publishing `command.invoke` signals (`dispatch`).
- Emits optional command hook signals (`jido.hooks.pre`, `jido.hooks.after`).

## Guides

- [Getting Started](./getting-started.md)
- [Command Declarations](./command-declarations.md)
- [Hooks and Signals](./hooks-and-signals.md)
- [Permissions and Allowed Tools](./permissions-and-allowed-tools.md)
- [Settings](./settings.md)
- [CLI Usage](./cli.md)
- [Elixir API Usage](./elixir-api.md)
- [Troubleshooting](./troubleshooting.md)

## Architecture contract

For strict runtime signal and validation contracts, see:

- [`docs/architecture/contracts.md`](../architecture/contracts.md)
