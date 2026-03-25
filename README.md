# Macro

This package contains **macros** used in the `Pass` project.

## LocalizedMacro

A freestanding expression macro that converts a static string literal into a localized string, with optional format arguments and bundle support.

## Usage

### Basic localization

```swift
#localized("Hello world")
// expands to:
String(localized: "Hello world")
```

### With format arguments

```swift
#localized("Hello %@", "world")
// expands to:
String(format: String(localized: "Hello %@"), "world")

#localized("Version %@ (%d)", "1.0.0", 5)
// expands to:
String(format: String(localized: "Version %@ (%d)"), "1.0.0", 5)
```

### With a custom bundle

```swift
#localized("Hello world", bundle: .module)
// expands to:
String(localized: "Hello world", bundle: .module)

#localized("Hello %@", bundle: .module, "world")
// expands to:
String(format: String(localized: "Hello %@", bundle: .module), "world")
```

## Requirements

- Swift 6.0+
- macOS 12+, iOS 15+, tvOS 15+, watchOS 8+

## Installation

Add this package as a dependency in your `Package.swift`:

```swift
.package(url: "<repo-url>", from: "<version>"),
```

Then add `"Macro"` to your target's dependencies.
