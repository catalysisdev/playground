# Learning Mix

In this directory I'm going through the [introduction to Mix](https://elixir-lang.org/getting-started/mix-otp/introduction-to-mix.html#our-first-project) tutorial to better understand Elixir's primitives, mental models, and tooling.

## Notes

### Project structure
- `mix` is the standard build tool that comes with Elixir.
- A project can be initialized by running `mix new myproject --module MyProject` where the second argument is the name of the project and the flag value passed through `--module` the name of the project's main module.
- The manifest of the project is in `mix.exs`. The equivalent is equivalent to `Package.swift`, `package.json`, and `.gemspec` in other ecosystems.

### Compiling and running
- The main module is created under `lib`.
- `mix compile` compiles the project.
- `iex -S mix` runs the interactive shell with the project loaded in it.

### Testing
- Tests are placed under `test`
- Tests are executed with `mix test`.
- We can run the test by passing the path as the first argument of `mix test`. We can also specify a particular line within the test file with the `:{line}` suffix in the path.   

### Code formatting
- Elixir ships with code formatter and the configuration lives in `.formatter.exs`.
- The formatting is triggered with `mix format`.


### Environments
- Mix has the notion of environments: 
  - `dev`: the one used by default
  - `test`: the one used when running tests 
  - `prod`: the one used when the project runs on production
- The environment can be obtained through `Mix.env()`, which returns the environment as an atom: `:dev`, `:test`, `:prod`
- The environment can be set when invoking mix by setting environment variables: `MIX_ENV=prod`