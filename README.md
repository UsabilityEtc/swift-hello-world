# swift-hello-world

A simple Swift Hello, World example that imports a Swift package ([swift-greeting](https://github.com/jeffreymorganio/swift-greeting)) as a dependency.

## The Package

The `HelloWorld` package declares its dependency on the `SwiftGreeting` package in its `Package.swift` file using the URL of the `SwiftGreeting` package, which is https://github.com/jeffreymorganio/swift-greeting.git:

```
import PackageDescription

let package = Package(
  name: "HelloWorld",
  dependencies: [
      .Package(url: "https://github.com/jeffreymorganio/swift-greeting.git", majorVersion: 1)
  ]
)
```

`main.swift` imports the `SwiftGreeting` package to enable it to use the `Greeting` class, which is defined in the `SwiftGreeting` package:

```
import SwiftGreeting

let greeting = Greeting(greeting: "Hello, World!")
greeting.outputGreeting()
```

Note that the name of the `SwiftGreeting` package is declared in its [Package.swift](https://github.com/jeffreymorganio/swift-greeting/blob/master/Package.swift) file:

```
import PackageDescription

let package = Package(
    name: "SwiftGreeting"
)
```

and is therefore independent of the name of the repository, which is `swift-greeting`.

## Building

After cloning this repository, to build the `HelloWorld` package first `cd` into `swift-hello-world` and then type:

```
swift build
```

## Running

After building the `HelloWorld` package, type:

```
.build/debug/HelloWorld
```
