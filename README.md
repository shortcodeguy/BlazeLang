# BlazeLang

**High-Performance Programming Language with Native C++ Core, Integrated AI, & Mathematical Computing**

Official Website: [blazelang.web.app](https://blazelang.web.app)  
Developer & Maintainer: **ShortCodeGuy Studio**

---

## Overview

BlazeLang is an extensible programming language engineered for execution speed, low memory overhead, and developer ergonomics. The project has evolved from an early prototype into a **native C++ implementation**, featuring integrated capabilities for mathematical computation, AI primitives, HTTP networking, and package management.

The language design emphasizes self-sufficiency — enabling high-level AI and scientific workflows without mandatory dependencies on heavy third-party frameworks.

---

## Key Features

- **C++ Native Core**: Lightweight interpreter and execution runtime written in native C++.
- **Integrated AI & Math Capabilities**: Built-in primitives for tensor math, numerical computing, and AI helper utilities.
- **Native Networking**: Integrated HTTP/HTTPS client and server modules.
- **Ecosystem Tooling**: Includes `blaze` CLI package manager, test runner, and registry integration.
- **Modular Extensions**: Support for C++ native extensions and custom module bindings.

---

## Ecosystem Architecture

```text
BlazeLang/
├── registry/          # Package registry manifests & modules
├── src/               # Native C++ core engine & interpreter
├── include/           # Header definitions & API bindings
├── stdlib/            # Standard library modules (Math, HTTP, AI, IO)
├── tools/             # Package manager & test runner binaries
└── docs/              # Language specifications & syntax documentation
```

---

## Getting Started

### Prerequisites
- C++17 compliant compiler (`g++`, `clang++`, or `MSVC`)
- CMake 3.16+ (or Make)

### Building from Source

```bash
git clone https://github.com/shortcodeguy/BlazeLang.git
cd BlazeLang
mkdir build && cd build
cmake ..
make
```

---

## License & Attribution

Distributed under the MIT License. See `LICENSE` for details.

Developed by **Rohit Raj (ShortCodeGuy)** — [ShortCodeGuy Studio](https://shortcodeguystudio.netlify.app)
