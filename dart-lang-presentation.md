#!/usr/bin/slides
---
<!-- theme: https://github.com/charmbracelet/glamour/raw/master/styles/pink.json -->
author: Nathan Angelo B. Cruz
---

# Welcome to Dart

```dart
void main() {
  var teacher = "Sir Credo";

  print("Hi CS!");
  print("Hello ${teacher}!");
}
```

---

# What is Dart?

- **Blazing fast**
- A client-optimized language for developing fast apps on any platform
- Object-oriented and functional programming paradigms
- Supports just-in-time compilation to **web**, **mobile**, and **desktop**
- Sound typing system
- Null safety
- Async support

---

# Why Dart?

- Open-source
- [Flutter](flutter.dev), a framework for cross-platform user interfaces
  - An alternative to React Native
- A modern syntax similar to the likes of Java and JavaScript (ES6)
- First class language tools (LSP, linter, formatter)
- [pub](pub.dev), a robust package management system

---

# Why not Dart?

- Google
- You don't like OOP

---

# A Deep Dive Down Dart

---

# History

- First announced at the GOTO conference in Aarhus, Denmark in 2011
- Creators: Lars Bak and Gilad Bracha (Google Inc.)

## First stable 1.0 release: November 14, 2013

- Dart Editor, an IDE
- Dartium, a custom version of Chromium with a Dart VM
- dart2js, translates Dart to JavaScript
- Pub, package manager

---

## Flutter revealed: 2015

- The open source framework for cross-platform UIs that uses Dart
- High performance
- Runs jitter-free on Android and iOS
- Uses widgets which are components to build the UI
- Hot reload

---

## Dart 2.0: 2018

- Strong, sound typing
  - Type inference
- Improved integration with web and mobile technologies

---

## Flutter 1.0: 2018

- Tooling support for editors
- "Add to App" functionality to onboard existing apps <!-- What this essentially did was streamline the process to adding Flutter to an app. So you could have an Android and/or iOS app, run this feature, and you could start using Flutter.  -->
- Platform-specific views and technologies

---

## Dart 3 alpha: Coming soon

- Sound null safety system
  - Breaking change
- Records
  - Anonymously composite values
  - Similar to objects in JavaScript and dictionaries in Python
- Patterns
  - Syntactic sugar
  - For destructuring records

---

# Development

## Latest Versions

### 2.19

- Updating packages and providing further documentation
- Guides for Dart coming from another language (Swift, JavaScript)
- Flow analysis to determine unreachable code

---

## Variations and Features

- A client-optimized language for developing fast apps on any platform ... paired
with a flexible execution runtime platform for app frameworks
- Sub-second stateful hot reload
- Just-in-time compiler
- Garbage collection
- Compiles to web, mobile, and desktop

---

- Sound typing system
  - Checks to make sure that each variable always matches the static type assigned
  - Flexible enough for type inference and dynamic types
- Null safe
  - Must specifically designate that a value can be nullable
- [Pub](pub.dev)
  - Package management
- Asynchronous programming
  - Futures
    - Similar to promises in JavaScript
  - Async/await
- Object-oriented programming
- Language tooling

---

## Hardware

- ARM32
- ARM64
- x86_64
- JavaScript
- In short, **cross-platform**

---

## Application Area/s

- Well-suited for “a technical envelope that is particularly suited to client development, prioritizing both development (sub-second stateful hot reload) and high-quality production experiences across a wide variety of compilation targets (web, mobile, and desktop).”

---

## Characteristics

- Open-source
- Type safe
- Statically typed
- Null safe
- Client-optimized
- Cross-platform

---

## Classification

- Class-based
- Single-inheritance
- Pure object-oriented
  - Everything except `null` is an object

---

## Translator Program

### Hybrid Compiled and Interpreted

- Compiles to target platform
  - Web: translated to JavaScript
  - Native: includes VM with JIT and ahead-of-time compilation for machine code
- When apps are run, it does so through the Dart runtime
  - Manages memory
  - Enforces type safety
  - Handles asynchronous code

---

# Data-Level Structures
