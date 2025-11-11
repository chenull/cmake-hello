# CMake Hello World (Apple ARM64 + Linux x86_64)

This repository contains a minimal CMake project that prints a hello world
message. Two toolchain files are provided to help target Apple ARM64 and
Linux x86_64 platforms.

## Prerequisites

- CMake 3.20 or newer
- C/C++ compilers:
  - `clang` / `clang++` for Apple ARM64
  - A cross-compiler such as `x86_64-linux-gnu-gcc` / `x86_64-linux-gnu-g++`
    for Linux x86_64 builds from macOS

## Building

### Native Apple ARM64 build

```bash
cmake -S /Users/ayik/Dev/Nix/cmake-hello -B /Users/ayik/Dev/Nix/cmake-hello/build/apple-arm64 \
  -DCMAKE_TOOLCHAIN_FILE=/Users/ayik/Dev/Nix/cmake-hello/toolchains/apple-arm64.cmake
cmake --build /Users/ayik/Dev/Nix/cmake-hello/build/apple-arm64
```

### Cross-compiling for Linux x86_64

Make sure the specified cross compilers are installed (for example via Homebrew
`brew install x86_64-elf-gcc` or another toolchain).

```bash
cmake -S /Users/ayik/Dev/Nix/cmake-hello -B /Users/ayik/Dev/Nix/cmake-hello/build/linux-x86_64 \
  -DCMAKE_TOOLCHAIN_FILE=/Users/ayik/Dev/Nix/cmake-hello/toolchains/linux-x86_64.cmake
cmake --build /Users/ayik/Dev/Nix/cmake-hello/build/linux-x86_64
```

## Running

After building, run the executable from the corresponding build directory:

```bash
/Users/ayik/Dev/Nix/cmake-hello/build/apple-arm64/hello_cmake
```

or

```bash
/Users/ayik/Dev/Nix/cmake-hello/build/linux-x86_64/hello_cmake
```

