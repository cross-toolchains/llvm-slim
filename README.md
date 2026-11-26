<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://api.iconify.design/simple-icons/llvm.svg?color=%23ffffff" />
  <source media="(prefers-color-scheme: light)" srcset="https://api.iconify.design/simple-icons/llvm.svg?color=%23000000" />
  <img src="https://api.iconify.design/simple-icons/llvm.svg?color=%23000000" height="56" alt="LLVM" />
</picture>

<h1>llvm-slim</h1>

**Minimal, portable, multi-target LLVM (`clang` + `lld` + binutils) prebuilt binaries for Linux, macOS, and Windows.**

Built directly from upstream [llvm/llvm-project](https://github.com/llvm/llvm-project) using official LLVM CMake distribution flags — no `lldb`, no `clangd`, no static LLVM dev libraries.

</div>

---

## What's Inside

Each `llvm-slim-<version>-<target>` archive contains only the stripped runtime tools needed for cross-compiling C, C++, Rust, and Go to Linux, Windows MSVC, macOS, iOS, Android, OpenHarmony, and WebAssembly:

- **Compilers**: `clang`, `clang++`, `clang-cl`
- **Linkers**: `lld`, `ld.lld` (ELF), `ld64.lld` (Mach-O), `lld-link` (PE/COFF), `wasm-ld` (Wasm)
- **Binutils**: `llvm-ar`, `llvm-ranlib`, `llvm-objcopy`, `llvm-strip`, `llvm-nm`, `llvm-lib`, `llvm-dlltool`, `llvm-rc`
- **Headers**: `lib/clang/<major>/include` (`clang-resource-headers`)
- **Targets enabled**: `X86`, `AArch64`, `ARM`, `RISCV`, `WebAssembly`

## Supported Hosts

| Host Triple | Archive Format |
| :--- | :--- |
| `x86_64-unknown-linux-gnu` | `llvm-slim-<ver>-x86_64-unknown-linux-gnu.tar.xz` |
| `aarch64-unknown-linux-gnu` | `llvm-slim-<ver>-aarch64-unknown-linux-gnu.tar.xz` |
| `aarch64-apple-darwin` | `llvm-slim-<ver>-aarch64-apple-darwin.tar.xz` |
| `x86_64-apple-darwin` | `llvm-slim-<ver>-x86_64-apple-darwin.tar.xz` |
| `x86_64-pc-windows-msvc` | `llvm-slim-<ver>-x86_64-pc-windows-msvc.zip` |

## Usage

Recommended via [`xllvm`](https://github.com/cross-toolchains/xcompiler):

```sh
xllvm install 23.1.6
```

Or download directly from [Releases](https://github.com/cross-toolchains/llvm-slim/releases).

## Triggering a Build

Push a tag matching `llvm-<version>` (e.g. `llvm-23.1.6`) or run the **Build llvm-slim** workflow manually via `workflow_dispatch`.

## License

- Build scripts and workflows in this repository are dual-licensed under `MIT OR Apache-2.0`.
- Distributed LLVM binaries are licensed under the upstream [Apache-2.0 WITH LLVM-exception](https://llvm.org/LICENSE.txt).
