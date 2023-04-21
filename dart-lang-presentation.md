#!/usr/bin/slides
---
author: Nathan Angelo B. Cruz
---
<!-- This file is meant to be used with the slides CLI app, but being -->
<!-- a markdown file, it can simply be read that way -->

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

## Constants and Variables

- `var`: Initializes a variable; automatically infers type
- `Type`: Explicitly declares type
- `final`: Can be set only once; typing is optional
- `const`: Compile-time constants; typing is optional

Difference between `final` and `const`?

`final` objects may have fields and attributes modified;
`const` objects may not

```dart
var variable = 1;
String hello = "world";
final arr = [1, 2, 3];
arr = [4, 5, 6]; // Not possible
```

---

## Data Types

Everything in Dart is an object, i.e. they implement the `Object` class. The only exception is `null`, which is the only type that is not an object.

The language is soundly typed through static type and runtime checks. Thus, a variable can never be a type it was not annotated or inferred to be.

### Built-in

- Numbers: `int` (integers) and `double` (double-precision floating point)
- Booleans: `bool` (`true` or `false`)

### Enumerated

- Created through the `enum` keyword
- Values accessed through the `.` (dot) operator
- Dart 2.17: Introduced enhanced enums
  - Supports fields, methods, and constructors like classes

```dart
var number = 1.5;
var boolean = true;
number.ceil(); // -> 2
boolean.toString(); // -> "true"

enum example {
  up,
  down,
}

example.up; // -> example.up
```

---

## Data Structures

- `String` is immutable
  - `StringBuffer` contains manipulation methods
- `List` is an ordered collections of objects
  - Similar to arrays
- `Set` is like `list` but each element is unordered and unique
- `Map` stores data in key-value pairs
  - Similar to dictionaries and associative arrays
  - Can serve as trees and graphs
- `List`, `Map`, and `Set` are iterables

```dart
var string = "Hello World";
var list = [1, 2, "Three"];
var setExample = {5, 4, 3};
var map = {
  "test": "example",
  1: 2,
};
```

---

## Abstract Data Types

- `class` defines a class
  - Constructors
  - Instance members
  - Static members
- `abstract` defines an abstract `class`
  - Used to make interfaces with the `implements` keyword
  - Methods do not have a body
- `extends` can be used to make a class inherit from another
  - Methods can be overridden with the `@override` metatag
- `operator` followed by the symbol can override operators
- Private variables and methods start with an `_` (underscore)
- Optional variables have a `?` (question mark) after their type
- `get` and `set` define getters and setters
- Constructors are methods with the same name as the class
- `this` accesses instance variables and methods

---

```dart
abstract class ExampleContainer {
  void sayHello();
}

class Example implements ExampleContainer {
  String name;
  int? nullableVariable;
  static double staticVariable = 1.1;

  Example(this.name, this.nullableVariable);  // Constructor

  void sayHello() {
	print("Hello!");
  }

  String get greeting {
	return "My name is: ${this.name}";
  }

  void set lastName(String lastName) {
	this.name = "${this.name} ${lastName}";
  }

  Example operator +(Example second) {
	return Example(this.name + second.name, second.nullableVariable);
  }
}
```

---

## File Structures

- `File` is constructed with the path to a file on the system
  - Operations
    - Opened
    - Closed
    - Read
    - Written
    - Created
    - Deleted
    - Checked for existence
  - Has convenience methods like `readAsString()`
    - Synchronous and asynchronous
- `Stream` is returned when a `File` is read
  - Can read a `File` line by line
  - Can be written and appended to

```dart
File myFile = File('hello.txt');
if (!myFile.existsSync())
	myFile.create();
myFile.readAsString().then((value) {
	print(value); 
});
```

---

# Program-Level Structures

## Character Set

- UTF-16

```dart
var smile = "😃";
```

---

## Operators

### Symbols and Meaning


