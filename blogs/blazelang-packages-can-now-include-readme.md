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
readTime: "2 min read"
featuredImage: "/logo.jpg"
status: "published"
---

BlazeLang Packages Can Now Include README.md

BlazeLang package development is becoming more developer-friendly.

Package developers can now include a README.md file inside their packages to document what the package does, how to install it, how to use it, and what APIs it provides.

Why README.md?

A package should explain itself.

When developers discover a BlazeLang package, they should be able to quickly understand:

What the package does
How to install it
How to import it
What functions or classes it provides
How to use it
Any important requirements or configuration

A README.md provides a standard place for this documentation.

Example Package Structure

A package can now contain documentation alongside its BlazeLang source files:

my-package/
├── README.md
├── main.blz
├── utils.blz
└── package.json

The README can use standard Markdown.

For example:

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
Documentation Ships With the Package

One important advantage is that the documentation stays together with the package itself.

Developers don't have to maintain a separate documentation location just to explain a small package. The package can contain both the implementation and its documentation.

This is particularly useful for smaller utilities, libraries, and experimental packages.

Better Package Discovery

README files also make packages easier to understand before developers start working with their source code.

A good README can provide:

A description of the package
Installation instructions
Basic usage examples
Available APIs
Configuration information
Known limitations

This gives users the information they need without requiring them to read the entire implementation.

A Simple Convention

BlazeLang doesn't need every package to have a large documentation website.

For many packages, a simple README.md is enough.

The important part is that developers have a predictable place to explain their package.

Building the BlazeLang Ecosystem

As the BlazeLang package ecosystem grows, developer experience becomes increasingly important.

Package managers can handle installation and distribution, but documentation helps developers understand what they installed.

With README.md support, BlazeLang packages can ship their code and documentation together.

Write the package. Document the package. Share the package.
