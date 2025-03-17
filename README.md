# this-vs-that

| This | That |
| --- | --- |
| **scaledToFill()**: focuses solely on filling the frame without regard to the aspect ratio. | **aspectRatio(contentMode: .fill)**: ensures the aspect ratio is preserved during the scaling process. |
| **padding()**: should be added on entire view component like VStacks, not on each individual item inside the stack. | **stack-spacing**: Applies equal spacing on items inside stacks, much better and cleaner implementaion. |
| **VStack**: Eagerly loads all child views at once, Works well when all content is visible on the screen, suitable for small lists, Can cause performance issues if used with a large number of views because all items are rendered upfront. | **LazyVStack**: Loads views lazily, meaning only the views currently visible (and a few offscreen for smooth scrolling) are loaded, Ideal for large lists of content or *pagination*, usually accompanied by ScrollView. |
| **.ignoresSafeArea**: Expands to cover the entire screen, (iOS 14+) ✅, Can specify which edges to ignore and the affected regions (e.g., container, keyboard). | **.edgesIgnoringSafeArea**: (Deprecated) ❌ since iOS 14, Limited to safe area ignoring. |
| **ForEach**: Loops over data to create views, Good for static views. | **List**: Creates a scrollable list, Optimized for large, dynamic lists. |
