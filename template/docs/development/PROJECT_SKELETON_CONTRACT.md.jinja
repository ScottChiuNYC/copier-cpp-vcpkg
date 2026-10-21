# Project Skeleton Contract

Contract version: 1.0
Template: `copier-cpp-vcpkg` (pure C++ CMake/vcpkg library)

## 1. Purpose and authority

This is the normative **project skeleton** contract for the generated C++ repository. It describes **where** code, tests, dependencies, packaging, and CI belong. A separate domain Essence describes **what** the library must implement: public behavior, algorithms, numerical semantics, and acceptance requirements.

Agents must read both documents before adding implementation. The generated project's local copy is authoritative for its skeleton; when a project intentionally changes a skeleton convention, update this document alongside that change. This contract does not itself add scientific accuracy or test thresholds.

## 2. Ownership and directory layout

- `include/{{ project_slug }}/`: public C++ headers included by internal and downstream clients.
- `src/`: production C++ sources; `src/CMakeLists.txt` uses recursive `GLOB_RECURSE CONFIGURE_DEPENDS` for `*.cpp` below this directory. Nested implementation sources are automatically discovered; new targets still require explicit CMake wiring.
- `tests/`: GoogleTest C++ tests; the baseline `tests/CMakeLists.txt` discovers top-level `*.cpp`. Nested tests or multiple executables require CMake changes.
- `examples/`: illustrative consumers, not substitutes for acceptance tests.
- `cmake/LibraryConfig.cmake.in`: CMake package config template.
- `vcpkg-ports/{{ vcpkg_port_name }}/`: source-relative local library port recipe and port manifest.
- `vcpkg-ports/gtest/`: pinned local GoogleTest overlay.
- `docs/development/`: specification, design, audit journal, and execution evidence—not executable inputs for the build, tests or code generation.

The skeleton owns build integration, build scripts, source locations, test wiring, dependency and package mechanics, CI workflows, and supported build modes. The domain Essence owns the actual C++ APIs, algorithms, application scope, required external capabilities and acceptance behaviors. Do not add hidden domain logic to CMake or workflow YAML.

## 3. CMake, public targets and consumers

The root `CMakeLists.txt` enables C++{{ cpp_standard }} and CTest. It delegates to `src/`, `examples/` when `BUILD_EXAMPLES=ON`, and `tests/` when `BUILD_TESTING=ON`.

By default `BUILD_STATIC_LIBRARY=ON` and `BUILD_SHARED_LIBRARY=ON` build the independent `{{ project_slug }}` and `{{ project_slug }}_shared` targets. Their headers are provided through `include/` with distinct build-tree and install-tree paths. Compiled libraries install under standard GNU install directories, headers under `include/`, and the relocatable package config/version/targets under `lib/cmake/{{ project_slug }}/`. Downstream consumers call `find_package({{ project_slug }} CONFIG REQUIRED)` and link `{{ project_slug }}::{{ project_slug }}`. A direct install may expose both the static and shared imported targets.

The version for the CMake package is the `version` Copier answer and uses same-major-version compatibility. Use target-specific `target_link_libraries`, include paths, compile options and features when extending the library; do not silently replace its target/API packaging.

## 4. vcpkg and packaging

`vcpkg.json` describes the development/build dependencies (including GoogleTest). `vcpkg-configuration.json` sets the pinned Microsoft registry and local overlay ports. Keep an added production C++ dependency declared where needed, including the local library port manifest if downstream consumers require it. Avoid ad hoc registry changes and preserve the configured vcpkg baseline unless a migration is explicitly intended.

The local `vcpkg-ports/{{ vcpkg_port_name }}/portfile.cmake` builds from the current source tree. It chooses static or shared according to `VCPKG_LIBRARY_LINKAGE`, disables examples/tests, installs the library's own public CMake package, and does not package development-only dependencies. This local port must remain within the source checkout. Changes to public headers or packaging must be validated by an **independent downstream C++ consumer**, not inferred from a source-tree build.

If the public API changes, update the example and `tests/vcpkg-consumer/` to consume the new API; verify relocated install behavior and Debug/Release consumers. Changes to linkage/export behavior require their own verification.

## 5. Build, tests and CI

Use the canonical scripts from a fresh environment:

```bash
python scripts/bootstrap.py
python scripts/validate.py
```

The bootstrap pins tools and vcpkg; validate configures/builds, executes CTest and validates the vcpkg consumer. `CMakePresets.json` owns supported Windows/Linux configure/build/test preset names. Use the existing CMake and GoogleTest integration for domain acceptance tests, not duplicate custom build pathways.

The generated `.github/workflows/build-and-test.yml` runs this pipeline on Linux and Windows on push and pull request **unless all changed files are within `docs/development/`**. Mixed changes and all relevant code, test, CMake, dependency or workflow changes must still run. `workflow_dispatch` remains available. This exception assumes the directory contains **non-executable development documents/evidence only**; put inputs consumed by build, tests or code generation outside it. Update this policy if that assumption changes.

The template repository's own `.github/workflows/template-acceptance.yml` continues to run normal platform acceptance for template source changes, including Copier copy/update, build, tests and packaging. Do not apply the generated-project path exclusion to template acceptance.

## 6. Interface with the domain Essence

Domain requirements can name logical components, public APIs, mathematical conditions, dependencies or tests. Map them onto the skeleton directories and targets above. Do not interpret silence in the Essence as authorization to introduce unrelated architectures, performance requirements, numerical thresholds or project infrastructure. If an Essence requirement genuinely conflicts with this contract, surface the conflict and record a deliberate resolution rather than silently changing either authority.
