# Support VS Code, PlatformIO, C++20

As of October 2025, the `ms-vscode.cpptools` extension's `clang-tidy` feature, PlatformIO, and C++20 don't play together. Although binaries can be built with the appropriate build flag/unflags, PlatformIO doesn't forward the C++20 configuration to clang-tidy, which results in erroneous errors.

To fix this problem, an extra script can be used to run `pio run --target compiledb` to generate `compile_commands.json` for clang-tidy.


## Required

1. Add flags for C++ standard and `compiledb.py`
2. Copy `compiledb.py` into your project directory
3. Configure the `"C_Cpp.codeAnalysis.clangTidy.args"` VS Code setting (example in the `.vscode` folder).

The `-p` argument for clang-tidy should be set to the directory `compile_commands.json` will end up in. This cookbook example uses the workspace root.
