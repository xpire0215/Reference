# SwiftUI

## Specify Preview Devices

add .previewDevice(PreviewDevice(rawValue: "device_name")) to the View.

Also, .previewDisplayName("device_name") could change the display name of the preview device.

```
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
            .previewDevice(PreviewDevice(rawValue: "iPad"))
            .previewDisplayName("iPad")
    }
}
```
