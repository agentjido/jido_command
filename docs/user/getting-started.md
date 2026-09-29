# Historical Setup Reference

> Do not use these steps for new work. This repository is deprecated, unsupported, and read-only. The steps remain only to explain the final source state.

This guide records the development setup that was used before retirement.

## 1. Fetch historical development dependencies

```bash
mix deps.get
```

## 2. Create local runtime directory

`jido_command` reads local files from `<cwd>/.jido_code`.

```bash
mkdir -p .jido_code/commands
```

## 3. Add your first command

Create `.jido_code/commands/hello.md`:

```markdown
---
name: hello
description: Say hello
---
Hello {{name}}.
```

## 4. Start the app

```bash
iex -S mix
```

At startup, the application supervises:

- `Jido.Signal.Bus`
- `Jido.Code.Command.Registry`
- `Jido.Code.Command.Dispatcher`

## 5. List commands

From another shell:

```bash
mix run -e 'Jido.Code.Command.CLI.main(["list"])'
```

You should see `hello` in the output.

## 6. Invoke the command

```bash
mix run -e 'Jido.Code.Command.CLI.main(["invoke", "hello", "--params", "{\"name\":\"Pascal\"}"])'
```

You can also invoke from Elixir:

```elixir
Jido.Code.Command.invoke("hello", %{"name" => "Pascal"})
```

## Runtime roots and precedence

The registry loads commands from:

- Global root: `~/.jido_code/commands/*.md`
- Local root: `<cwd>/.jido_code/commands/*.md`

Local commands override global commands when names collide.

## Next

- Define richer commands in [Command Declarations](./command-declarations.md)
- Configure runtime behavior in [Settings](./settings.md)
