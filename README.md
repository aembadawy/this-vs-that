# this-vs-that

| This | That |
| --- | --- |
| **scaledToFill()**: focuses solely on filling the frame without regard to the aspect ratio. | **aspectRatio(contentMode: .fill)**: ensures the aspect ratio is preserved during the scaling process. |
| **padding()**: should be added on entire view component like VStacks, not on each individual item inside the stack. | **stack-spacing**: Applies equal spacing on items inside stacks, much better and cleaner implementaion. |
| **VStack**: Eagerly loads all child views at once, Works well when all content is visible on the screen, suitable for small lists, Can cause performance issues if used with a large number of views because all items are rendered upfront. | **LazyVStack**: Loads views lazily, meaning only the views currently visible (and a few offscreen for smooth scrolling) are loaded, Ideal for large lists of content or *pagination*, usually accompanied by ScrollView. |
| **.ignoresSafeArea**: Expands to cover the entire screen, (iOS 14+) ✅, Can specify which edges to ignore and the affected regions (e.g., container, keyboard). | **.edgesIgnoringSafeArea**: (Deprecated) ❌ since iOS 14, Limited to safe area ignoring. |
| **ForEach**: Loops over data to create views, Good for static views. | **List**: Creates a scrollable list, Optimized for large, dynamic lists. |
| **.id()**: Manually assigns an ID to a view, When using *ForEach* on non-identifiable data. | **Identifiable** *Protocol*: Requires objects to have an *id* property, When working with identifiable models. |
| **.lineLimit(n)**: Limits number of visible lines, Used to prevent overflow. | **.truncationMode(.tail/.head/.middle)**: Controls how text is truncated	Choose how cut-off text appears. |
| **.textInputAutocapitalization(_:)**: Introduced in iOS 15 ✅, Offers better support and more flexibility. | **.autocapitalization(_:)**: Works on TextField and other text inputs, Deprecated in iOS 15 ❌. |
| **TextField**: Used for entering normal text, The entered text is visible, Can be customized with keyboard types, autocapitalization, and text formatting. | **SecureField** *(For Passwords & Sensitive Data)*: Used for entering secure/sensitive information like passwords, The entered text is **hidden**, Does **not** support features like autocapitalization or autocorrection. |
| **.sheet()**: Shows a *modal sheet* with swipe down to dismiss by ***default***, used for temporary interactions (e.g., forms, settings). | **.fullScreenCover()**: Covers the entire screen, and requires explicit dismissal. Dedicated full-screen flows (e.g., onboarding, authentication). |
| **@State**: Used to create and manage mutable state within a view. It allows you to store and track changes to a value so that your view can automatically update whenever that value changes. | **@Binding**: Used for creating a two-way connection between a property's value in one view and its| value in another view or a parent view. It's typically used to pass data between views and synchronize changes bidirectionally. |

# lazy-vs-computed-property

## Lazy Variable

Lazy variable is only computed once when accessed. Perfect for use when the variable requires heavy computation.

## Computed Property

Computed property is recalculated each time it's accessed. And unlike *lazy var* they don't store the value. Instead they provide a getter and an optional setter to indirectly retrieve and set values.

| Lazy Variable | Computed Property |
| --- | --- |
| Deferred Initialization: They are initialized only once, and only when they are first accessed. | Dynamic Calculation: They recalculate their value every time they’re accessed. |
| Storage: After its initial calculation, the lazy variable retains its value and does not recompute. | No storage: Computed properties do not store the computed value. |
| Optimal for Expensive Operations | Reflect Changing State: Useful when the property value depends on other variables and can change over time. |
| Thread Safety Concerns: Lazy variables are not thread-safe by default, which means care must be taken when using them in a multithreaded context. | Thread Safety: Computed properties are just calculations and don’t have inherent thread safety issues, but the properties they rely on might. |


`Comparison base on medium article` [here](https://mehrdad-ahmadian.medium.com/ios-interview-question-lazy-variables-vs-computed-properties-in-swift-b35fd323cbbd)
