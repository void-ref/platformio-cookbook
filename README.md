# PlatformIO Cookbook

Recipes to get you cooking faster.


## Support VS Code, PlatformIO, C++20

As of October 2025, the `ms-vscode.cpptools` extension's Clang-Tidy feature, PlatformIO, and C++20 don't play together. Although binaries can be built with the appropriate build flag/unflags, PlatformIO doesn't forward the C++20 configuration to clang-tidy, which results in erroneous errors.

Use the project structure in [`vscode_cxx20`](cxx20_clangtidy) to fix this problem.
