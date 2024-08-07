# C++ project template

Features:

- VCPKG for package management.
- CMake with CMakePresets for cross-platform builds.
  - Configuration presets:
    - `ninja`: A generic Ninja Multi-Config preset.
    - `clang`: A Clang specific Ninja Multi-Config preset.
    - `cl`: (Windows x64) CL specific Ninja Multi-Config preset.
    - `win64`: (Windows x64) Visual Studio 2022 preset.
  - Build presets:
    - Debug, RelWithDebInfo, and Release build presets are provided for all configuration presets above. Just add `debug`, `relwithdebinfo`, or `release`. For example, the presets for `clang` are `clang-debug`, `clang-relwithdebinfo`, and `clang-release`.
  - Test presets:
    - Just add `test-` to the build presets names.
- Clang-Tidy and Clang-Format.
- GitHub Action for reproducible builds.
  - 2 layers of cache: GitHub Actions Cache (`x-gha`) and GitHub Packages cache (`nuget`)
  - GitHub Actions cache should just work™️.
  - GitHub Packages cache requires you to create a Personal Access Token (classic) with `write:packages` permissions and saved to "Action Secrets" as a "Repository Secret" named `GH_PACKAGES_TOKEN`.
