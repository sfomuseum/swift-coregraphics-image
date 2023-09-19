# swift-coregraphics-image

Swift package providing a common interface for derive `CGImage` instances from `URL` instances in both an AppKit and UIKit context.

## Documentation

Documentation is incomplete.

## Example

```
            var cg_im: CGImage

            let im_rsp = CoreGraphicsImage.LoadFromURL(url: fileSaveUrl as URL)
            
            switch im_rsp {
            case .failure(let error):
                self.logger.error("Failed to load image, \(error)")
                return .badRequest(.text("Invalid image"))
            case .success(let im):
                cg_im = im
            }
```	    