#design #frontend
# How to size texts?
## Units of measurement
There's `px`, `pt`, `dp` and `sp`. Each one has its one particularity. But in the end, it doesn't matter much. 
- `px`: It can be understood as the minimal unit of light in a device's screen or the minimal unit of light that can be lit by software. Most design tools, like Figma and Sketch, use the meaning of CSS Pixel. Which is the web measurement for a minimal unit of light. So this can be your standard concept.
- `pt`, `dp` and `sp`
	- `pt` can be understood as the CSS Pixel for iOS. There are some differences, but in practice, they don't affect your work.
	- `dp` is the CSS Pixel for everything that is not text on Android.
	- `sp` is the CSS Pixel for texts on Android. There are two different units, because there can be users which increase their device's text size, and thus only the `sp` (*scalable pixel*) unit will be changed.
	- 
## Main size
**It's all about legibility. You cannot have a specific sizes as your silver bullets.** Some font styles will be readable with 16px, others will only be okay at 18px and some will be too big at 16px. Given that, a good place to start picking your design's size is **16px**.

The main size is what you will use on most of the text in your design. It should be as readable as the text in a well-printed book, held in a proper and natural distance.

Your process could be something like this:
1. Choose a good font for your context.
2. Start with 16px main size.
3. Consider *going smaller* if your application is interaction-heavy or the font has large, easy-to-read characters.
4. On the other hand, when going larger, you can be looser. But you should strongly consider, when your page is text-heavy or the font is hard to read.
### Text inputs
iOS browsers will zoom in if your text-input is smaller than **16px**. So, that is a good reason to set this value as your minimal size for inputs. Another thing to consider, is if your website wouldn't look weird having different font-sizes for normal text and inputs.

## Secondary size
Only one point smaller than your main size, would be difficult to notice. A good rule-of-thumb is going two points smaller and styling the text so that is clear it is less important.
