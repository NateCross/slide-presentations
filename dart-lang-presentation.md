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

---

### Built-in

- Numbers: `int` (integers) and `double` (double-precision floating point)
- Booleans: `bool` (`true` or `false`)

### Enumerated

- Created through the `enum` keyword
- Values accessed through the `.` (dot) operator
- Dart 2.17: Introduced enhanced enums
  - Supports fields, methods, and constructors like classes

---

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

---

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

Boolean | 
--- | ---
`\|\|` | or
`&&` | and

- When using boolean operators, both sides must evaluate to `boolean` or it will cause an error

---

The following groups of operators do not have any set definition

Rather, their purpose is to call the overloaded operator as defined by the class of the object


Relational |
--- |
`>=` |
`<=` |
`<` |
`>` |

Bitwise |
--- |
`^` |
`&` |

Shift |
--- |
`>>` |
`<<` |
`>>>` |

---

Additive |
--- |
`+` |
`-` |

Multiplicative |
--- |
`*` |
`/` |
`%` |
`~/` |

Unary |
--- |
`-` |
`~` |
`!` |

Postfix and Prefix |
--- |
`++` |
`--` |

---

```dart
void main() {
  if (false || true) {
    print("True!"); // -> True!
  } else {
    print("False!");  // This block is unreachable
  }

  print("Hello " + "World!");  // -> Hello World!
}
```

---

### Rules of Precedence

| Description    | Operator                           | Associativity | Precedence |
| -------------- | ---------------------------------- | ------------- | ---------- |
| Unary postfix  | e., e?., e++, e–, e1[e2], e()      | None          | 16         |
| Unary prefix   | -e, !e, ~e, ++e, await e           | None          | 15         |
| Multiplicative | *, /, ~/, %                        | Left          | 14         |
| Additive       | +, -                               | Left          | 13         |
| Shift          | <<, >>, >>>                        | Left          | 12         |
| Bitwise AND    | &                                  | Left          | 11         |
| Bitwise XOR    | ^                                  | Left          | 10         |
| Bitwise OR     | `\|`                                 | Left          | 9          |
| Relational     | <, >, <=, >=, as, is, is!          | None          | 8          |
| Equality       | ==, !=                             | None          | 7          |
| Logical AND    | &&                                 | Left          | 6          |
| Logical Or     | `\|\|`                             | Left          | 5          |
| If-null        | ??                                 | Left          | 4          |
| Conditional    | e1 ? e2 : e3                       | Right         | 3          |
| Cascade        | ..                                 | Left          | 2          |
| Assignment     | =, *=,  /=, +=, -=, &=, ^=, etc.   | Right         | 1          |

```dart
void main() {
  var example = 5;
  print(++example * 3 == 20 - 2);  // -> true
}
```

---

## Delimiters

- `;` (Semicolon): ends statements
- `\` (Backslash): escape characters
- `,` (Comma): separates arguments, parameters, and enumerated data
- `:` (Colon): used in a `Map` to separate key and value

```dart
var variable = 1;
String hello = "Hello World!\n";
var sum = add(1, 2);
var object = {
  'key': 'value',
};
```

---

## Separators or Brackets

- `()` (Parenthesis): groups expressions, denotes parameters and arguments, control flow
- `[]` (Square Brackets): create `List` access members of an object, denote optional parameters
- `{}` (Curly Brackets): mark blocks of code, create `Set` and `Map`, denote optional named parameters, string interpolation
- `<>` (Angle Brackets): annotate type of generics, can be nested
- `""` (Double Quotes): String literal, can be interpolated
- `''` (Single Quotes): String literal, cannot be interpolated

```dart
var addition = add(3, 4);
List<int> numbers = [1, 2, 3];
if (numbers.isNotEmpty) {
  print("Not empty!");  // -> Not empty!
}
```

---

## Text Format

Dart is freely formatted

```dart
var num = 1; print(num); // -> 1
```

---

## Appearance for Readability

- Two spaces for indentation per the style guide
- Ignores whitespace
- No preference on blank lines
- `//` (two forward slashes): make the rest of the line after it a comment
- `/* */` (forward slash and asterisk): multiline comment

```dart
// This is a comment
/* This is a 
  multiline comment */
```

---

## Punctuation

- `.` (Period): access members of an object
- `?` (Question Mark): used before period to access member if not null, also signifies variable is nullable
- `!` (Exclamation Mark): indicates that function will not return null
- `=>` (Arrow): creates arrow functions
- `..` (Two Periods): accesses multiple methods consecutively
- `$` (Dollar Sign): string interpolation

```dart
void main() {
  print(1.isOdd); // -> true
  print("${1..isOdd..isEven}"); // -> 1
  int? number;
  var addTwoNum = (int num1, int num2) => num1 + num2;
  print(addTwoNum!(1, 2)); // -> 3
}
```

---

## Words

- Identifiers may start with a letter or underscore, followed by letters, underscores, or numerical digits
  - Identifiers that start with an underscore are private

---

Below are the keywords in the language.

| Descriptive                |                                                                                |
|----------------------------|--------------------------------------------------------------------------------|
| `abstract`                 | abstract class, for interfaces                                                 |
| `async`                    | marks a function as asynchronous                                               |
| `class`                    | initializes a class                                                            |
| `final`                    | declares a variable that is set only once                                      |
| `const`                    | declares a variable that is a compile-time constant                            |
| `deferred`                 | lazy loads libraries to reduce startup time                                    |
| `while`, `do while`, `for` | loops                                                                          |
| `if`, `else`               | control flow                                                                   |
| `enum`                     | enumerations                                                                   |
| `extends`                  | creates a subclass                                                             |
| `super`                    | lets subclass access superclass                                                |
| `factory`                  | used for a constructor that does not create an object of the class             |
| `true`, `false`            | boolean values                                                                 |
| `get`, `set`               | declares getters and setters in a class                                        |
| `late`                     | allows for a variable to be non-nullable that is initialized after declaration |

---

| Descriptive                |                                                                                |
|----------------------------|--------------------------------------------------------------------------------|
| `mixin`                    | for sharing attributes with other classes                                      |
| `null`                     | default value of uninitialized variables and its own object type               |
| `operator`                 | overload operators in a class                                                  |
| `required`                 | marks required parameters in functions                                         |
| `static`                   | denotes class-wide variables and methods                                       |
| `sync`, `async`            | generator functions which produce a series of values                           |
| `switch`, `case`, `default`            |  switch statement                          |
| `this`                     | refers to attributes of the specific instance of the object                    |
| `typedef`                  | type alias                                                                     |
| `var`                      | declaring variables                                                            |
| `void`                     | return type signifying nothing is returned                                     |

---

| Action                             |                                                                            |
|------------------------------------|----------------------------------------------------------------------------|
| `assert`                           | stops execution when a condition is false, and used for testing            |
| `await`                            | used in an `async` function, pauses execution until a `Future` is returned |
| `break`                            | stops loops                                                                |
| `continue`                         | skips to the next iteration of a loop                                      |
| `try`, `catch`, `finally`, `throw` | handle exceptions                                                          |
| `import`                           | accesses a library                                                         |
| `show`, `hide`                     | uses a portion of a library                                                |
| `new`                              | constructs an instance of a class                                          |
| `return`                           | returns data from a function or method                                     |
| `yield`                            | returns values from a generator function                                   |

---

| Noise |                                           |
|-------|-------------------------------------------|
| `as`  | type casting                              |
| `is`  | returns true if object has the given type |
| `on`  | handle exceptions in code                 |

---

```dart
void main(List<String> args) {
  var _identifier = "";

  print((1 as double).isNaN); // -> false

  assert(true != false);


  for (var num in [1, 2, 3]) {
    if (num == 3) {
      print(num); // -> 3
      break;
    } else {
      continue;
    }
  }

  switch (1) {
    case 1:
      print(1); // -> 1
      break;
    default:
      print("Unreachable");
  }

  try {
    var api = await fetchApi();
  } catch(e) {
    throw "Fetch exception";
  }

  var sampleObject = new inheritedClass(4);

  while (true) {
    print(null);
  }

}
```

---

```dart
typedef strList = List<String>;

abstract class exampleClass {}

class inheritedClass extends exampleClass {
  late int number;
  static int staticVariable = 2;
  inheritedClass(this.number);

  factory inheritedClass.num(int num) {
    return inheritedClass(num + 1);
  }

  set numSquared(int num) {
    this.number = num * num;
  }

  get numAsDouble {
    return (number as double);
  }
}

enum exampleEnum {
  zero,
  one,
}
```

---

## Statements

- Declaration uses the following keywords
  - `var`: variable, type inferred upon assignment
  - `Type`: variable, type explicitly declared
  - `class`
  - `function`
- Assignment occurs with the `=` sign
  - The language currently does not support destructuring objects
- Arithmetic statements make use of the operations
- Input and output is handled by the `dart:io` package
  - `print()` to output in the command line
  - `stdout`, `stderr`, and `stdin` are accessible
  - `stdout.write()` to print to `stdout`
  - `stdin.readLineSync()` to receive input as a string
- Control statements have condition in parentheses, then a block in curly brackets to be executed
  - `if`, `else`, `if else`
  - `switch`, `break`
  - `while`, `do while`, `for`

```dart
import 'dart:io';
var assign = (stdin.readLineSync() as int);
if (assign == 1) {
	print(assign);
} else if (assign == 2) {
	assign++;
}
```

---

## Subprograms

- Variables are lexically scoped
  - But no distinction between global and local variables
- Subprograms are functions and methods
  - Have the supertype `Function`
  - May or may not have type annotations to parameters and return value
  - If there is no return value, it returns `null`
  - May be passed as arguments to other functions and methods
  - Functions with one expression can be written with the arrow syntax
  - Anonymous functions do not have an identifier, only a list of parameters
  - Parameters may be required, optional, named, and positional
- Programs must have one top-level `main()` function that returns `void`
- Subprograms are defined in Dart's core libraries
  - Importable through `import`
  - `dart:async`: asynchronous programming
  - `dart:core`: types, collections, other standard features
  - `dart:math`: mathematical operations
  - `dart:io`: access files and streams

---

```dart
void main(List<String> args) {
  var total = sumOfNumbers(1, 2);
  {
    var newTotal = total + 1;
  }
  print(newTotal);  // -> Undefined
}

int sumOfNumbers(int num1, int num2, [int num3 = 0]) => num1 + num2 + num3;

void greet(String greeting, {required String firstName, required String lastName}) {
  print("$greeting, $firstName $lastName!");
}
```

---

## Program Abstraction

- Modules can be imported through `import`
  - Packages can be downloaded from [Pub](pub.dev) or `dart pub add` in the command line
- Variables can be made private by making the first character of the identifier an underscore
  - Private variables can be accessed within the same library and all other classes within that library

```dart
import 'dart:io';
import 'utils.dart';

var _privateVariable = 1;
```

---

## Self-Documenting Features

- Dart's comprehensive toolset strongly enforces the use of its style and formatting
- Its SDK contains modern features
  - code actions
  - formatter
  - linter
  - supported by several code editors

```dart
class UpperCamelCase {}

void main(List<String> args) {
  var lowerCamelCase = 1;
  if (true) {
    print("Use curly braces for control flow statements.");
  }
}
```

---

# Control-Level Structures

## Expressions

- Evaluating an expression either produces an object or throws an exception
- Arithmetic and boolean expressions invoke their respective arithmetic operators on objects
- Boolean expressions must evaluate to a `bool`

```dart
int num1 = 1, num2 = 2;
double num3 = 3.5;
print(num1 + num2); // -> 3
print(num1 + num3); // -> 4.5 (double)

if (false && true) {
  print("Unreachable");
} else {
  print("False!"); // -> False!
}
```

---

## Control Statements

### Unconditional Branch

- Labels can be used as targets for `break` and `continue`

```dart
first: for (int i = 0; i <= 9; i++) {
  second: for (int j = 9; j >= 0; j--) {
    if (j % 3 == 0) {
      continue second;
    } else if (j % 5 == 0) {
      continue first;
    }
    print("$i $j"); // -> 0 8; 0 7; 1 8; 1 7; ...
  }
}
```

---

### Selection

- `if` and `else` perform two-way selection
- Chained `if` and `else` can perform multi-way selection
- `switch` can also do multi-way selection

```dart
if (true) {
  print("This is true!"); // -> This is true!
} else {
  print("This is false.");
}

switch (1) {
  case 1:
    print("1"); // -> 1
    break;
  default:
    print("This is default");
    break;
}
```

---

### Iteration

- `while`: conditionally iterate, test before
- `do while`: conditionally iterate, test after
- `for`: indexed iteration
- `for in`: iterate over an iterable

---

```dart
for(int i = 1; i <= 10; i++) {
  print(i); // -> 1; 2; 3; 4; 5; ...
}

for (var i in [1, 2, 3, 4, 5]) {
  print(i); // -> 1; 2; 3; 4; 5
}

var counter = 1;
while(counter <= 10) {
  print(counter); // -> 1; 2; 3; 4; 5; ...
  counter++;
}

do {
  print(counter); // -> 11; 10; 9; 8; 7; ...
  counter--;
} while (counter >= 1);
```

---

### Control over Program Execution

- `try`-`catch`-`finally` checks for execution errors

```dart
try {
  var api = await fetchApi();
} on NoApiException {
  print("No API fetched.");
} catch(e) {
  print("Caught unknown exception: $e");
} finally {
  cleanupApi();
}
```

---


## Subprogram Control Structures

### Simple Call/Return

- Functions and methods are the subprograms
- Declared with an identifier, followed by the signature and body
- May include a return type
- If they do not return anything, they return `null`
- `getters` in a class do not contain parameters

```dart
String makeGreeting(String firstName, String lastName) {
  return "Hello, $firstName $lastName!";
}
```

---

### Recursion

- Recursion works by calling the subprogram within itself
- Evaluated like a stack

```dart
int fibonacci(int num) {
  if (num <= 1) return num;
  return (fibonacci(num - 1) + fibonacci(num - 2));
}
```

---

### Implicit Call

- An example of this is a constructor method to create an instance of a class

```dart
class Greeter {
  String firstName;
  String lastName;

  Greeter(this.firstName, this.lastName);

  void greet() {
    print("Hello, $firstName $lastName!");
  }
}
```

---

### Parallel Processes

- `Stream` from the `dart:async` library allows a process to run in parallel
- Dart takes advantage of multi-core CPUs to run code in **isolates** which are their own memory heap
  - Removes the need for mutexes and semaphores

```dart
Future<int> totalStream(Stream<int> stream) async {
  int total = 0;
  await for (var num in stream) {
    total += num;
  }
  return total;
}
```

---

### Coroutines

- Declaring a function to be `async` allows the use of `await` which handles execution asynchronously until the data of a `Future` is received
  - A `Future` is a promise to return data, similar to `Promises` in JavaScript

```dart
Future<String> fetchGreeting(String firstName, String lastName) {
  return Future.delayed(
    const Duration(seconds: 2),
    () => "Hello, $firstName $lastName!",
  );
}
```

---

# End of Presentation
