# swift-coregraphics-image

Swift package providing a common interface for derive `CGImage` instances from `URL` instances in both an AppKit and UIKit context.

## Example

```
import CoreGraphicsImage

let im_url = URL(...)
let im_rsp = CoreGraphicsImage.LoadFromURL(url: im_url)
     
if case .success(let cg_image) = im_rsp {
    // do something with cg_image here
}
```

## Motivation

SFO Museum often writes tools in Swift that we would like to run in both a MacOS (`AppKit`) and iOS (`UIKit`) contexts. Because each respective framework has its own image type (`NSImage` and `UIImage` respectively) and each framework is specific to their respective platform this can result in a lot of fiddly-code when cross-compiling applications.

This package provides a single method (`LoadFromURL`) which accepts a `URL` instance and returns a CoreGraphics `CGImage` instance for the image at that location, regardless of platform.

That's all it does. How many people have already written this code? I'd wager a lot of people have. Now we have too.
