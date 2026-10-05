# service-weft-warp-burrito

An Elixir host that runs a sandboxed RISC-V guest through a NIF, one supervised process per guest machine, released as a single executable.

## What it is for

Each guest call is one of a fixed set of named capabilities, run under a fuel budget the emulator enforces, and a process serves one call at a time. The repository also carries the hierarchical task planner and its NIF as subtrees and a vendored actor runtime. Its own design records are in `rfd/`, and RFD 2304 in manuals-weftspun covers the planner copy.

## Build and run

The NIF and the guest build through `elixir_make`, with the RISC-V GCC toolchain and `mingw32-make` on the path:

```sh
mix deps.get
mix release
```

## Licence

MIT; see LICENSE. Vendored code keeps its own licence.
