# Rotary

![](https://img.shields.io/badge/platform-tvOS%2BiOS-blue)
![](https://img.shields.io/badge/swift-5.3-blue)

A wheel-like UI control component for choosing options from a menu.

# Demo

Tap the following image to launch [Appetize](https://appetize.io). The source for the demo app is available [here](https://github.com/nashysolutions/RotaryDemo).

<p align="center">
    <a href="https://appetize.io/app/udgkzhrukbwe3umq7x17h4zpjw?device=iphonex&scale=75&orientation=portrait&osVersion=12.2&deviceColor=black">
        <img src="https://user-images.githubusercontent.com/51816980/59976306-660b8f00-95ba-11e9-89d6-1862f6ee78da.png" alt="Preview"/>
    </a>
</p>

## Usage

```swift
import Rotary

struct Dancer: WheelOption {
    let name: String
    var wheelOptionTitle: String {
        return name
    }
}

let wheelControl = RotaryWheelControl<Dancer>()
wheelControl.rotationEnded = { [unowned self] dancer in
    self.label.text = "The current selection is \(dancer.name)"
}
wheelControl.layout([
    Dancer(name: "Joanne"),
    Dancer(name: "Stacey"),
    Dancer(name: "Rhian"),
    Dancer(name: "Cathy"),
    Dancer(name: "Robin")
    ])
wheelControl.styling = RotaryWheelStyling(
                                    font: <placeholder>,
                                    textColour: <placeholder>,
                                    spindleColour: <placeholder>,
                                    backgroundColour: <placeholder>,
                                    innerGrooveColour: <placeholder>,
                                    outerGrooveColour: <placeholder>
                                )
view.addSubview(wheelControl)
```

> The closure 'rotationEnded' is called immediately after layout. If you do not want this behaviour, call layout before assigning the closure.

# Installation

List this in your `Package.swift` manifest file as a [Swift Package](https://swift.org/package-manager/) dependency. [Releases Page](https://github.com/nashysolutions/Rotary/releases/).

# Acknowledgment 

Heavily influenced by the awesome team over at [raywenderlich.com](https://www.raywenderlich.com/2953-how-to-create-a-rotating-wheel-control-with-uikit).
