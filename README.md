# clang-tidy-test

Test project for refactoring experiments using [clang-tidy]
and related tools e.g. [autotidy].

## Quickstart

1. Run CMake to [generate] clang tooling [compile_commands.json] database

```
cmake -S . -B _build
```

2. Run `clang-tidy/tool/run-clang-tidy.py`

```
run-clang-tidy-7.py -p=_build -header-filter=test/.* > clang-tidy.log 2>&1
```

The script executes [clang-tidy] with the default set of checks on
every translation unit in the [compile_commands.json] and
displays the resulting warnings and errors.

3. Run [autotidy] to start interactive refactoring sesion.


[autotidy]: https://github.com/sasq64/autotidy
[clang-tidy]: http://clang.llvm.org/extra/clang-tidy/
[compile_commands.json]: https://clang.llvm.org/docs/JSONCompilationDatabase.html
[generate]: https://cmake.org/cmake/help/latest/variable/CMAKE_EXPORT_COMPILE_COMMANDS.html
