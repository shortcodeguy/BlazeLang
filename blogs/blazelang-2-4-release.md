---

title: "Announcing BlazeLang 2.4: Improved Packages and Developer Ecosystem"
slug: "blazelang-2-4-release"
subtitle: "A major package ecosystem update with improved package management, publishing, authentication, registry integration, and developer workflows."
excerpt: "ShortCodeGuy Studio is proud to announce BlazeLang 2.4, bringing major improvements to package management, registry integration, CLI authentication, and package publishing."
category: "Release Notes"
author: "ShortCodeGuy Studio"
role: "Language Creator and Core Architecture"
publishedAt: "2026-09-21"
updatedAt: "2026-09-21"
tags:

* release
* v2.4
* packages
* registry
* cli
* ecosystem
* official
  readTime: "6 min read"
  featuredImage: "/logo.jpg"
  status: "published"

---

# Announcing BlazeLang 2.4: Improved Packages and Developer Ecosystem

Today, **ShortCodeGuy Studio** is proud to officially announce **BlazeLang 2.4**.

This release focuses on one of the most important parts of a programming language ecosystem: **packages**.

BlazeLang 2.4 brings improvements to package management, registry integration, CLI authentication, package publishing, and the overall developer workflow.

### Developed by ShortCodeGuy Studio

BlazeLang is designed, architected, and maintained by **ShortCodeGuy Studio** as a clean, high-performance programming language for modern application and systems development.

## A Better Package Experience

BlazeLang 2.4 improves the complete package workflow.

Developers can create packages, authenticate with the BlazeLang ecosystem, publish `.blzp` packages, and install packages directly through the BlazeLang CLI.

The goal is simple:

> Packages should feel like a native part of BlazeLang.

## Improved Package Management

The BlazeLang CLI provides a more complete package management experience in version 2.4.

Packages can be installed directly using:

```text
blz install <package>
```

Specific package versions can also be requested:

```text
blz install <package>@<version>
```

This gives developers better control over package versions and dependencies.

## Registry Integration

BlazeLang 2.4 provides improved integration between the BlazeLang CLI and the official package registry.

The registry handles package information, versions, and distribution while the CLI provides a simple interface for developers.

This allows BlazeLang packages to be discovered and installed without manually downloading package files.

## CLI Authentication

BlazeLang 2.4 introduces an authentication workflow for the CLI.

Developers can log in using:

```text
blz login
```

After authentication, the current account can be checked with:

```text
blz whoami
```

When the session is no longer needed, developers can log out using:

```text
blz logout
```

This authentication system provides the foundation for secure package publishing.

## Package Publishing

BlazeLang 2.4 also introduces an improved package publishing workflow.

Developers can publish a `.blzp` package using:

```text
blz publish <package-path.blzp>
```

The CLI sends the package to the BlazeLang registry for processing.

This allows package authors to publish directly from their development environment instead of manually uploading package files.

## The `.blzp` Package Format

BlazeLang packages are distributed using the `.blzp` format.

The format provides a structured way to package BlazeLang projects for distribution through the registry.

With the improved package ecosystem in 2.4, `.blzp` becomes an important part of the BlazeLang development workflow.

## A Complete Package Workflow

The package workflow in BlazeLang 2.4 can be summarized as:

```text
Create
  |
Build
  |
Package as .blzp
  |
Login
  |
Publish
  |
Registry
  |
Install
  |
Use
```

The objective is to make the entire process simple and consistent.

## Built on the Native C++ Foundation

BlazeLang 2.4 continues to build on the native C++ architecture introduced in BlazeLang 2.2.

The native runtime provides the foundation for the BlazeLang CLI, while version 2.4 expands the ecosystem surrounding the language.

This allows BlazeLang to evolve beyond the runtime itself and provide a more complete developer platform.

## What BlazeLang 2.4 Brings

BlazeLang 2.4 focuses on:

* Improved package management
* Better registry integration
* CLI authentication
* Account management through the CLI
* `.blzp` package publishing
* Better package distribution
* A more complete developer workflow

These improvements make it easier for developers to work with packages throughout the entire BlazeLang ecosystem.

## Looking Forward

BlazeLang 2.4 establishes a stronger foundation for the BlazeLang package ecosystem.

As more packages and developers join the ecosystem, the registry and CLI provide the infrastructure needed to distribute and manage BlazeLang packages efficiently.

**BlazeLang 2.4 is an ecosystem-focused release built around packages, tooling, and developer experience.**

### BlazeLang 2.4

**Native language.
Native tooling.
Native package ecosystem.**

Built by **ShortCodeGuy Studio**.
