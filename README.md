# "Change" refactoring kata in C++

[![CI](https://github.com/Coding-Cuddles/change-refactoring-cpp-kata/actions/workflows/main.yml/badge.svg)](https://github.com/Coding-Cuddles/change-refactoring-cpp-kata/actions/workflows/main.yml)
[![C++17](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.cppreference.com/w/cpp/17)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## Overview

This kata complements [Clean Code: Fundamentals, Ep. 2 - Names++](https://cleancoders.com/episode/clean-code-episode-2).

## Instructions

The goal of this kata is to refactor the `ChangeItForMe` class methods for
better variable names, structure, and readability. You cannot change the
signatures of the class methods or tests.

Refactor the C++17 implementation without changing its observable behavior.
Setup is complete when both existing tests pass.

## Prerequisites

Required:

- [Git](https://git-scm.com/downloads)
- A compiler with C++17 support. Choose one:
  - [GCC](https://gcc.gnu.org/) 10+ on Linux
  - [LLVM Clang](https://llvm.org/) 14+ on Linux
  - [Apple Clang](https://developer.apple.com/xcode/) 17+ on macOS
  - [MSVC](https://visualstudio.microsoft.com/) 2022 on Windows
- [CMake 3.24 or later](https://cmake.org)

Optional:

- [GNU Make](https://www.gnu.org/software/make/), for shorter commands. Every
  required task also has direct CMake and CTest commands. Make may be
  unavailable on Windows.

You do not need to install GoogleTest separately. CMake finds an installed
copy or downloads the pinned release when needed.

## Set up the kata

1. Clone the repository:

   ```console
   git clone https://github.com/Coding-Cuddles/change-refactoring-cpp-kata.git
   ```

2. Enter the repository directory:

   ```console
   cd change-refactoring-cpp-kata
   ```

3. Build and run the tests. Use Make when it is installed:

   ```console
   make test
   ```

   Otherwise, use CMake and CTest directly:

   ```console
   cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug
   cmake --build build --config Debug
   ctest --test-dir build --build-config Debug --output-on-failure
   ```

The first run may download and build GoogleTest. CTest should report
`100% tests passed` with two passing tests. If a command reports a missing
compiler or CMake, install that prerequisite and run the setup commands again.
Setup is complete when CTest reports `100% tests passed`.

## Work on the kata

Refactor `ChangeItForMe` in `change.h`. Keep the class method signatures and
the tests in `test_change.cpp` unchanged.

After each change, use Make when it is installed:

```console
make test
```

Otherwise, use CMake and CTest directly:

```console
cmake --build build --config Debug
ctest --test-dir build --build-config Debug --output-on-failure
```

Continue when CTest reports `100% tests passed`.

## Make command reference

Make is optional. Run `make` or `make help` to list these commands in the
terminal.

| Command             | Result                                    |
| ------------------- | ----------------------------------------- |
| `make all`          | Build and run the test suite              |
| `make help`         | List public Make targets                  |
| `make build`        | Configure and build without running tests |
| `make test`         | Build and run the test suite              |
| `make format`       | Format tracked C++ and header files       |
| `make format-check` | Check formatting without changing files   |
| `make clean`        | Remove generated build artifacts          |
