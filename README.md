# 🦮 Flutter Style Guide

Welcome to the Flutter Style Guide, a comprehensive manual designed to standardize and enhance the quality of my Flutter projects.
This guide provides clear conventions and best practices in Flutter development, ensuring that my code is not only high-performing and reliable but also easy to read and maintain.

> **🪶 Note:** Remember, this is a living document that evolves alongside our growing expertise and the ever-changing landscape of Flutter development. Your insights and suggestions are valuable in enriching this guide.

Let's dive in!

## Table of Contents

- [Variables](#variables)
- [Documentation](#documentation)
- [Naming Conventions](#naming-conventions)
- [Utility Classes](#utility-classes)
- [Architecture](#architecture)

## Variables

### Final vs Var

- **Prefer `final` over `var`** to enhance code readability and performance in certain scenarios:
  - **Performance**: In Dart's ahead-of-time (AOT) compilation, `final` variables can potentially be optimized more effectively.
  - **Readability**: `final` indicates that a variable will not be reassigned, making the code easier to understand.
- **Use `var` when**:
  - **Reassignment**: Variable value changes over time.
  - **Complex Types**: Type inference is complex, and explicit typing is less readable.
  - **Iterables/Streams**: Useful in iterations where types are inferred.
  - **Dynamic Nature**: When the variable type is inherently variable or unknown.

_Guideline: Use `final` for immutability and clarity, `var` for reassignment and dynamic scenarios._

## Documentation

### Dart-Doc Comments

- **Format**:
  - Ensure that there are spaces before and after Dart-doc comments.
    ```dart
    ///
    /// This is the documentation for the function, spare one line above and below for
    /// better readability
    ///
    void someFunction() {
        // do stuff here
    }
    ```
- **Usage Examples**:

  - In utility related interfaces, make sure to include an example of usage in Dart-doc comments to clarify usage of the code
    ````dart
    ///
    /// function docs here,
    ///
    /// ### Example:
    /// ```dart
    /// final bool sanitizedEmail = sanitizeEmail("my.email@mail.com");
    /// ```
    ///
    String sanitizeEmail(String email) {
        // function logic
    }
    ````

## Naming Conventions

### General

- Stick to Dart's standard naming conventions for consistency and readability, you can refer [here](https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#naming)

### File Naming

My file naming conventions are designed to streamline the structure of code in my projects.
Each file is named with a clear reference to its 'parent', facilitating easier tracking of where it's used.
This approach effectively utilizes sub-extensions or metadata, as you might call it, to create a coherent
and navigable codebase.

- **Standard Naming**:
  - Format: `name_context.type.parent.dart`
    - Example: `login_button.widget.login_screen.dart`
- **Test Files**:
  - Format: `parent/name_context_type_test.dart`
    - Example: `login_screen/login_button_ui_test.dart`

## Utility Classes

Utility classes are like my Swiss Army knife in coding.
Compact, static-method hubs for handy, reusable functions that keep my code neat and efficient.
No frills, just pure utility!

### Principles

- **Avoid Global Functions**: Encapsulate global functions in a class to structure them properly and minimize side effects.
- **Static Methods**:
  - Prefer static methods in utility classes to eliminate the need for object references.
  - Exceptions:
    - If a utility class contains private or interdependent methods, using static methods is optional.
    - Ensure uniformity in method implementation - avoid a mix of static and non-static methods in the same class unless necessary.

## Architecture

MVC Architecture is like having a well-organized kitchen in coding.
It separates the app into three interconnected parts,

- Model (the fridge, where data lives)
- View (the dining table, what users see and interact with)
- Controller (the chef, managing the logic). This setup makes modifying and maintaining each section simpler and more efficient.

### Separation of Concerns

- **UI vs Business Logic**:
  - Maintain a clear separation between UI (User Interface) and business logic.
  - This separation facilitates easier testing and maintenance.

---

I would love to hear your thoughts and would love to make improvements to this style guide. Happy Coding 💚
