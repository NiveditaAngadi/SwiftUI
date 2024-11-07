Reference: 
https://developer.apple.com/pathways/swiftui/

# SwiftUI
SwiftUI employs declarative programming, which focuses on writing your specific desired outcome and letting SwiftUI do the work of translating your code into a functional UI.

SwiftUI's combination of declarative syntax, live previews, and multi-device support provides everything you need to begin designing and developing for Apple platforms. 

1. Why SwiftUI is a great choice for creating apps?
2. The basics of developing apps with SwiftUI
3. How to develop and preview your SwiftUI apps in Xcode


   SwiftUI employs declarative programming, which focuses on writing your specific desired outcome and letting SwiftUI do the work of translating your code into functional UI.
   Writing declaratively can be a powerful tool for UI design as it allows you to more easily iterate on your ideas, and can make your code more succinct and readable.

   To get started watch "SwiftUI essentials"
   SwiftUI -> Apple's declarative user interface framework, used to build apps across all of Apple platforms.
   You can build brand new app with SwiftUI or incremental adoptation of an app with SwiftUI.

  1. Why SwiftUI? 
   SwiftUI is right choice while building brand new app. It comes with wide range of features.
   - SwiftUI comes with wide range of features,
   - these enable your apps to take advantange of the devices they run on,
   - feel native on Apple's platforms, and rich interactivity.
   - Adding these features requires less code
   - Enables to move from prototype to production faster.
   - Empowering you to focus on what makes your app unique.
   - Embraces incremental adoption

  2. How views work in SwiftUI?
     Views are the basic building blocks of user interfaces and are important to everything you do in SwiftUI.
     There are three qualities that make SwiftUI views special,
       - declarative
       - compositional
       - state-driven
    
     Views are expressed declaratively - you describe what view you want in your user interface and SwiftUI produces the result
     For example,

     HStack {
       Label("Whiskers", systemImage: "cat.fill")
       Spacer()
       Text("Tightrope walking")
     }

      List -> Scrollable collection of items.

     Declarative vs Imperative programming
     Decalrative and Imperative programming are not mutually exclusive. Declarative code enables you to focus on the expected result, instead of steps to get there.
     Imperative code is great when making a change to state, or when there might not be an existing declarative component.
     SwiftUI embraces both. Example of this is button. Buttons are added to the view declaratively, and part of this declaration is the action perform when tapped.
     This action uses imperative code to make a change.

     SwiftUI views are descriptions of what the current state of the UI should be they are not long lived object instances that receive imperative commands over time.
     This is why SwiftUI views are value types, defined using structs instead of classes.

     SwiftUI takes these descriptions and creates an efficient data structure to represent them. It maintains this data structure behind the scenes. And it's used to produce different outputs, for example, what is shown on the screen, the gestures and interactive aspects of the view and its accessibility representation.

     Composition -> Used throughtout SwiftUI and is essential part of every user interface.
     For example: Horizontal stack contains multiple views.
     This syntax uses a view builder closure, to declare the children of a container.

     HStack {
      Image(whiskers.profileImage)

      VStack(alignment: .leading) {
        Label("Whisker:, systemImage: "cat.fill")
        Text("Tightrope  walking")
     }

     Spacer()
 }

 Composition plays an important role in another SwiftUI pattern called "View modifiers"
 View modifiers apply modifications onto a base view and can change any aspect of that view. 
 
 Image(whiskers.profileImage)
    .clipShape(.circle)
    .shadow(radius: 3)
    .overlay {
        Circle().stroke(.green, lineWidth: 2) 
    }

  View hierarchies can be encapsulated into custom views and view modifiers. 
  ** Cuctom View ** confirms to the "View" protocol and has body property to return the view it represents. 
  You can refactor your view into custom view and use as is. 
  ForEach creates a view for element in the collection.

  Views are  *** State-driven *** when your view's state changes over time SwiftUI automatically keeps your UI up to date, eliminating both boilerplate and update bugs. 

  SwiftUI maintains the representation of user interface behind the scenes. As data changes new view values are created and given to SwiftUI. SwiftUI uses those values to determine
  how to update its outputs. 
  Any piece of data that a view uses in its body is a dependency of that view. 
  SwiftUI creates dependencies to the specific properties used in view bodies. 
  SwiftUI has several tools for state management. 
  1. @Observable class
  2. @State
  3. @Binding

  ** State ** - creates a new internal source of data for a view. When you mark a view property as @State, SwiftUI manages its storage and provides it back for the view 
  to read and write. 

  ** Binding **  - creates two-way reference to the state of some other view. 

  SwiftUI maintans the value of the state behind the scenes. 
  Animations are built on the data driven approach. 
  Default animation is cross-fade tansition. 

SwiftUI provides many built-in capabilities - giving higher starting point for building your app. 
SwiftUI provides adaptivity along several dimensions. 
- Dark mode support
- Supports several accessibility features - dynamic type, ready to be localized.
- Xcode previews - interactive, able to see the output without running code in simulator.

Benefit to SwiftUI's declarative views is adaptivity. Views provided by SwiftUI often describe the purpose of their functionality as opposed to their exact visual construction. 
Buttons are example for adaptive view. They adopt across different styles, such as borderless, bordered or prominent, automatically adapt to different contexts, such as swipe actions, menus and forms. 

SwiftUI's declarative and adaptive views pack in a lot of functionality in just a few lines of code. 

UI Controls -> Button, Toggle, Picker 
Container Views -> NavigationSplitView, TabView, Table 
Presentation Views -> Sheet, confirmationDialog, inspector 
Others -> Searchables, draggable, focusable

Another layer of API's provides low-level control
ButtonStyle, ToggleStyle, CustomHoverEffect
Canvas, SensoryFeedback, Group(subViewsOf:) 
Layout, Animation, TextRender
Shader, Material, visualEffect

You can build your own control styles, use Canvas for high performing imperative drawing, create completely custom layout, even apply custom metal shaders directly on SwiftUI Views. 

An App is a declarative structure defined by scenes. WindowGroup is one kind of scene. It's created with a content view to show on screen. 
Scenes can be composed together. 


SwiftUI's capabilities extends to any platforms - iOS, MacOS, iPadOS, tvOS, WatchOS, visonOS

Learn once. use anywhere.
Specialised API's for each platform. 

*** SDK interoperability ***
-> SwiftUI's ability to interoperability with features and capabilities of other frameworks.

SwiftUI is a framework that comes with each platform's SDK. 

UIKit and AppKit are imperative object oriented user interface frameworks. They provide similar building blocks as SwiftUI, but use different patterns for creating and updating views. 
SwiftUI -> seamless interoperability with UIKit and AppKit 
UIViewRepresentable -> UIView 
NSViewRepresentable -> NSView 
This can be used in SwiftUI code like any other views. 

In case if you want to user SwiftUI views in UIKit,  define a Hosting View Controller - this is created with root SwiftUI view, and can be added to your UIKit or AppKit view controller hierarchy. 

SwiftUI is built with a foundation of declarative, compositional, and state-driven views. On top of that it provides platform-idiomatic capabilities and integration with a wide SDK. All of these things help you focus on what makes your app unique, with less code provide a wide range of components that results in idiomatic and engaging applications. And enable incremental adoption along every step of the way. 
