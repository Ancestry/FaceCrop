# FaceCrop
CGImage extension that utilizes Apple's Vision Framework to detect and center faces.


![Example](https://user-images.githubusercontent.com/15527890/87205361-20506000-c2bc-11ea-919a-e0a788d5b303.png)


# Usage

```swift
cgImage.faceCrop { [weak self] result in
    switch result {
    case .success(let cgImage):
        DispatchQueue.main.async { self?.imageView.image = UIImage(cgImage: cgImage) }
    case .notFound, .failure( _):
        print("error")
    }
}
```
 
If you need to crop a `UIImage` - you can always access its `CGImage` by calling [.cgImage](https://developer.apple.com/documentation/uikit/uiimage/1624147-cgimage).

===

Huge thanks to Anastasios Grigoriou for his contribution to this project!
