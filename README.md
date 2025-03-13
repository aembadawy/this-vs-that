# this-vs-that

| This | That |
| --- | --- |
| **scaledToFill()**: focuses solely on filling the frame without regard to the aspect ratio. | **aspectRatio(contentMode: .fill)**: ensures the aspect ratio is preserved during the scaling process. |
| **padding()**: should be added on entire view component like VStacks, not on each individual item inside the stack. | **stack-spacing**: Applies equal spacing on items inside stacks, much better and cleaner implementaion. |
