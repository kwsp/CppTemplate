# C++ project template

Features:

- VCPKG for package management.
- CMake with CMakePresets for cross-platform builds.
  - Configuration presets:
    - `clang`: (Non-windows only) Clang + Ninja Multi-Config.
    - `win64`: (Windows x64 only) Visual Studio 2022.
    - `cl`: (Windows x64 only) CL Ninja Multi-Config.
    - `clang-cl`: (Windows x64 only) ClangCL Ninja Multi-Config.
  - Build presets:
    - Debug, RelWithDebInfo, and Release build presets are provided for all configuration presets above. Just add `debug`, `relwithdebinfo`, or `release`. For example, the presets for `clang` are `clang-debug`, `clang-relwithdebinfo`, and `clang-release`.
- Clang-Tidy and Clang-Format.
- GitHub Action for reproducible builds.
  - 2 layers of cache: GitHub Actions Cache (`x-gha`) and GitHub Packages cache (`nuget`)
  - GitHub Actions cache should just work™️.
  - GitHub Packages cache requires a Personal Access Token (classic) with `write:packages` permissions and saved to "Action Secrets" as a "Repository Secret" named `GH_PACKAGES_TOKEN`.
