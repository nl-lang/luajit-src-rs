# luajit-src for NL

This is [NL](https://github.com/nl-lang/nl)'s fork of [luajit-src], the crate
that [mlua-sys] uses to build LuaJIT. It builds [NL's fork of LuaJIT 2.1]
(`luajit2/`) together with NL's runtime library (`nl-runtime/`), which the VM
embeds. A Rust program that embeds NL patches mlua's `luajit-src` with it:

```toml
[patch.crates-io]
luajit-src = { git = "https://github.com/nl-lang/luajit-src-rs" }
```

`NL_RUNTIME_DIR` in the environment builds the VM with another runtime
directory instead.

This repository is kept in step with the NL repository: each NL commit names a
commit of this one (its `luajit-src-rs` submodule), whose `luajit2/` is the
fork at NL's `LuaJIT` submodule and whose `nl-runtime/` is a copy of NL's
`runtime/*.lua`. NL's `tests/vm/support/sync_luajit_src_rs.sh` updates both.

[luajit-src]: https://github.com/mlua-rs/luajit-src-rs
[mlua-sys]: https://crates.io/crates/mlua-sys
[NL's fork of LuaJIT 2.1]: https://github.com/nl-lang/LuaJIT

# License

This project is licensed under the [MIT license](http://opensource.org/licenses/MIT),
as are LuaJIT and NL.
