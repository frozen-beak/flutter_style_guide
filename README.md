# 🦮 Flutter Style Guide

We frontend developers often write and manage a significant amount of code, spending more time reading it than actually writing
or updating it. Therefore, readability is crucial. This style guide aims to establish standardized practices to achieve maximum
readability, making our codebase more maintainable and easier to work with.

As John Woods once said, _“Always code as if the guy who ends up maintaining your code will be a violent psychopath who knows where
you live.”_ So, let's make our code a joy to read and maintain!

> **🪶 Note:** This guide is a work in progress! It should evolve as we learn more and as Flutter's ecosystem evolves.
> Your ideas and suggestions matters. So, let's enjoy the journey! Also feel free to create a pull request if you have any
> updates or improvements to share.

## Table of contents

- [Naming Conventions](#naming-conventions)
- [Variables](#variables)
- [Documentation](#documentation)
- More coming soon!

## Naming conventions

Flutter has set of guidelines for us to follow to help us standardise naming conventions in our code.
Have a look at [Flutter's Official Guidelines for naming](https://github.com/flutter/flutter/wiki/Style-guide-for-Flutter-repo#naming)

Here are some of the guidelines enforced by "flutter_lints",

- Use descriptive names that convey the purpose of the variable, function, or class. For example,
  instead of `User` name it like `UserProfile` to add more knowledge
- Avoid using single-letter names for variables, except for simple loop counters.
- Avoid using reserved keywords or names that conflict with Dart or Flutter libraries.
- Begin global constant names with prefix "k", like `kApiUrl`.
- Do not name files with capital letters use underscores instead for improved readability.
  For example, `my_really_long_file.dart`
- Use camelCase while naming variables and functions like `myVariableName`
- Use TitleCase while naming classes and objects, like `UserProfile`

## Variables

- `final` vs `var`:

  Prefer the use of `final` variables over `var`. It helps to enhance code readability and performance in certain scenarios like
  _performance improvements_ and _reliability_. Use `var` only when _reassignment_ or _mutability_ is needed.

- Use of `const`:

  1. Prefer to use `const` when the value of the variable is immutable as well the value is constant. For example,
     `const id = 234;`.
  2. Prefer the use of `const` while initiating objects if they are constants, mainly for Data and Model classes.
     For example, `final userProfile = const UserProfile();`

## Documentation

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
