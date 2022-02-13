#design #frontend
# How to size texts?
## Units of measurement
There's `px`, `pt`, `dp` and `sp`. Each one has its one particularity. But in the end, it doesn't matter much. 
- `px`: It can be understood as the minimal unit of light in a device's screen or the minimal unit of light that can be lit by software. Most design tools, like Figma and Sketch, use the meaning of CSS Pixel. Which is the web measurement for a minimal unit of light. So this can be your standard concept.
- `pt`, `dp` and `sp`
	- `pt` can be understood as the CSS Pixel for iOS. There are some differences, but in practice, they don't affect your work.
	- `dp` is the CSS Pixel for everything that is not text on Android.
	- `sp` is the CSS Pixel for texts on Android. There are two different units, because there can be users which increase their device's text size, and thus only the `sp` (*scalable pixel*) unit will be changed.
## For web
**It's all about legibility. You cannot have a specific sizes as your silver bullets.** Some font styles will be readable with 16px, others will only be okay at 18px and some will be too big at 16px. Given that, a good place to start picking your design's size is **16px**.
