---
template: overrides/main.html
title: Samples
---

## Sample apps

There are two sample apps: Counter and Todo List.

### Sample counter app

This sample demonstrates the following features:
- Nested components
- Routing
- Reused components
- State preservation (using `StateKeeper`)
- Retaining instances (using `InstanceKeeper`)
- Pluggable UI (Android Views, Jetpack Compose, SwiftUI, JS React)

Content:
- [Shared module](https://github.com/arkivanov/Decompose/tree/master/sample/counter/shared) which includes the following components:
    - [Counter](https://github.com/arkivanov/Decompose/blob/master/sample/counter/shared/src/commonMain/kotlin/com/arkivanov/sample/counter/shared/counter/Counter.kt) - this component just increments the counter every 250 ms. It starts counting once created and stops when destroyed. So `Counter` continues counting while in the back stack, unless recreated. It uses the `InstanceKeeper`, so counting continues after configuration changes.
    - [CounterInnerContainer](https://github.com/arkivanov/Decompose/blob/master/sample/counter/shared/src/commonMain/kotlin/com/arkivanov/sample/counter/shared/inner/CounterInnerContainer.kt) - this component contains the `Counter` and two `Routers` on the left and on the right side. Each `Router` displays its stack of `Counters` and two buttons for navigation. "Next" button pushes another `Counter` to the corresponding `Router`, "Prev" button pops the active `Counter` for the `Router`.
    - [CounterRootComponent](https://github.com/arkivanov/Decompose/blob/master/sample/counter/shared/src/commonMain/kotlin/com/arkivanov/sample/counter/shared/root/CounterRootContainer.kt) - this component contains the `Counter`, the `Router` of `CounterInnerContainer` and a button pushing another `CounterInnerContainer` to the stack. System back button is used for backward navigation.
- [Android sample app](https://github.com/arkivanov/Decompose/tree/master/sample/counter/app-android)
- [iOS sample app](https://github.com/arkivanov/Decompose/tree/master/sample/counter/ios-app)
- [JavaScript sample app](https://github.com/arkivanov/Decompose/tree/master/sample/counter/app-js)

<img src="https://raw.githubusercontent.com/arkivanov/Decompose/master/docs/media/SampleCounterDemo.gif" width="196"> <img src="https://raw.githubusercontent.com/arkivanov/Decompose/master/docs/media/SampleCounterIos.png" width="196"> <img src="https://raw.githubusercontent.com/arkivanov/Decompose/master/docs/media/SampleCounterJs.png" width="196">

#### Sample Counter Component structure 

<img src="https://raw.githubusercontent.com/arkivanov/Decompose/master/docs/media/SampleCounterStructure.png" width="384">

### Sample Todo List app

This sample can be found in the JetBrains Compose repository [here](https://github.com/JetBrains/compose-jb/tree/master/examples/todoapp).

It demonstrates the following features:
- Multiplatform: Android, iOS and Desktop
- Shared JetBrains Compose UI for Android and Desktop apps
- SwiftUI for iOS app
- Nested components
- Shared routing with view state preservation
- Using `Lifecycle`
- Multi-module structure (one component per module)
- Inter-component communication (via [Reaktive](https://github.com/badoo/Reaktive), just an example)
- MVI using [MVIKotlin](https://github.com/arkivanov/MVIKotlin)
- Data persistance using [SQLDelight](https://github.com/cashapp/sqldelight)

Please refer to the sample's readme for more information.

## Articles

- [Decompose — experiments with Kotlin Multiplatform lifecycle-aware components and navigation](https://proandroiddev.com/decompose-experiments-with-kotlin-multiplatform-lifecycle-aware-components-and-navigation-a04ef3c7f6a3?source=friends_link&sk=f7d289cc329b6c8a765fc049e36c313f)
- [Fully cross-platform Kotlin applications (almost)](https://proandroiddev.com/fully-cross-platform-kotlin-applications-almost-29c7054f8f28?source=friends_link&sk=4619fdcb17912fde589bc4fca83efbbd)