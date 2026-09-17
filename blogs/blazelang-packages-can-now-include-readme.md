---
title: "BlazeLang Packages Can Now Include README.md"
slug: "blazelang-packages-can-now-include-readme"
subtitle: "Package developers can now ship a README.md with their BlazeLang packages, making installation, usage, APIs, and package documentation easier to discover."
excerpt: "Package developers can now ship a README.md with their BlazeLang packages, making installation, usage, APIs, and package documentation easier to discover."
category: "Ecosystem"
author: "ShortCodeGuy Studio"
role: "BlazeLang Creator & Developer"
publishedAt: "2026-09-17"
updatedAt: "2026-09-17"
tags:
  - BlazeLang
  - Packages
  - README
  - Developer Experience
  - Ecosystem
  - Documentation
readTime: "3 min read"
featuredImage: "/logo.jpg"
status: "published"
---

# BlazeLang Packages Can Now Include README.md

BlazeLang package development is becoming more developer-friendly.

Package developers can now include a `README.md` file directly inside their packages to document what the package does, how to install it, how to use it, and which APIs it provides.

---

## Why `README.md`?

A package should explain itself.

When developers discover a BlazeLang package, they should be able to quickly understand:

| Question                   | Documentation                  |
| -------------------------- | ------------------------------ |
| What does it do?           | Package description            |
| How do I install it?       | Installation instructions      |
| How do I import it?        | Import example                 |
| What does it provide?      | API documentation              |
| How do I use it?           | Usage examples                 |
| Does it have requirements? | Configuration and requirements |

A `README.md` provides a standard place for this documentation.

---

## Example Package Structure

A BlazeLang package can contain documentation alongside its source code:

```text
my-package/
├── README.md
├── main.blz
├── utils.blz
└── package.json
```

The important addition is:

```text
README.md
```

The file uses standard Markdown, allowing developers to use headings, lists, code blocks, tables, links, and other Markdown features.

---

## Example README

A simple BlazeLang package README could look like this:

```markdown
# My Package

A simple utility package for BlazeLang.

## Installation

blz install my-package

## Usage

Import MyPackage

Show(MyPackage.Add(10, 20))

## Features

- Utility functions
- Simple API
- BlazeLang implementation
```

This gives package users the essential information without requiring them to inspect the implementation first.

---

## Documentation Ships With the Package

One important advantage is that the documentation stays together with the package itself.

Developers don't need to maintain a separate documentation location just to explain a small package.

The package can contain both:

* Implementation
* Documentation

This is particularly useful for:

* Small utilities
* Libraries
* Developer tools
* Experimental packages
* Community packages

---

## Better Package Discovery

README files also make packages easier to understand before developers start working with their source code.

A good README can provide:

* **Description** — What the package is for
* **Installation** — How to install it
* **Usage** — How to use it
* **API Reference** — Available functions, classes, and features
* **Configuration** — Required settings or dependencies
* **Examples** — Practical usage
* **Limitations** — Known restrictions or issues

This allows developers to understand a package without reading its entire implementation.

---

## A Simple Convention

BlazeLang doesn't require every package to have a large documentation website.

For many packages, a simple:

```text
README.md
```

is enough.

The goal is to provide a predictable place for package documentation while keeping the package structure simple.

---

## Building the BlazeLang Ecosystem

As the BlazeLang package ecosystem grows, developer experience becomes increasingly important.

A package manager can handle installation and distribution, but documentation helps developers understand what they are installing.

With `README.md` support, BlazeLang packages can ship their code and documentation together.

> **Write the package. Document the package. Share the package.**
