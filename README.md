# swift-hello-world

A simple Swift Hello, World package that imports a Swift package ([swift-greeting](https://github.com/UsabilityEtc/swift-greeting)) as a dependency.

The Hello, World package package declares it's dependency on the `swift-greeting` package in it's `Package.swift` file:

```
import PackageDescription

let package = Package(
  name: "HelloWorld",
  dependencies: [
      .Package(url: "https://github.com/UsabilityEtc/swift-greeting.git", majorVersion: 1)
  ]
)
```

In `main.swift`, the `SwiftGreeting` package is imported to enable the code in `main.swift` to use the `Greeting` class:

```
import SwiftGreeting

let greeting = Greeting(greeting: "Hello, World!")
greeting.outputGreeting()
```

Node that the name of the `SwiftGreeting` package is declared in the [Package.swift](https://github.com/UsabilityEtc/swift-greeting/blob/master/Package.swift) file of the `swift-greeting.git` repository:

```
import PackageDescription

let package = Package(
    name: "SwiftGreeting"
)
```

and is therefore independent of the name of the repository.
