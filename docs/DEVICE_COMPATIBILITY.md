# Device & Platform Compatibility Report (Phase 0 Audit)

## Host & Toolchain Environment
- **Host OS**: macOS 27.0.1 (Darwin 27.0.0, arm64 Apple Silicon)
- **Xcode Version**: Xcode 27.1 (Build 27A9275)
- **Active SDKs**:
  - `iphoneos27.1`
  - `iphonesimulator27.1`
  - `macosx27.0`
- **Swift Version**: Swift 6.4 (swiftlang-6.4.0.34.1, Apple Swift 6.4)
- **Project Generator**: XcodeGen 2.46.0

## Target Device: iPhone Duo Verification
- **CoreSimulator Registration**:
  - Device Type Identifier: `com.apple.CoreSimulator.SimDeviceType.iPhone-Duo`
  - Model Identifier: `iPhone19,4`
  - Product Class: `V68`
  - Min Runtime Version: `27.1.0`
  - Display Feature Flags: `com.apple.CoreSimulator.display.resizableScene: true`
  - Hinge / Screen Architecture: Dual-region flexible display surface with posture detection.

## Available Public APIs in iOS 27.1 SDK
### UIKit Hinge API
Apple provides official hinge inspection headers in iOS 27.1:
1. `UIHinge.h` (`UIKIT_EXTERN NS_SWIFT_UI_ACTOR API_AVAILABLE(ios(27.1))`):
   - `UIHinge.Status`:
     - `.unknown` (0)
     - `.closed` (1)
     - `.partiallyOpen` (2) - Tabletop / Half-folded mode
     - `.fullyOpen` (3) - Flat unfolded mode
   - `angle: CGFloat` (in radians, from $0$ to $\pi$ or full extension)
2. `UIHingeInteraction.h`:
   - `UIHingeInteraction`: Subclass of `NSObject <UIInteraction>`. Added to any `UIView` to receive asynchronous hinge state updates.
   - `UIHingeInteraction.Update`: Yields the current `UIHinge?` snapshot.

### SwiftUI Integration Strategy
SwiftUI currently does not provide a direct `@Environment(\.hingeAngle)` macro in the standard library.
Therefore, DuoPlayer implements:
- `HingeReaderView`: A lightweight `UIViewRepresentable` hosting `UIHingeInteraction`.
- `FoldLayoutCoordinator`: A central observable coordinator bridging native `UIHinge` updates, window geometric aspect ratio transitions, and manual simulation controls for Xcode Previews and automated UI testing.

### Supported Postures & Layout Modes
1. **Compact Portrait (Folded Phone)**:
   - Aspect ratio: ~19.5:9 or narrow window.
   - Layout: Standard mobile UI, single-column media library, floating miniplayer or full-screen vertical player.
2. **Expanded Canvas (Unfolded Flat Tablet)**:
   - Aspect ratio: ~4:3 or near-square ($W/H \approx 0.9 \sim 1.3$).
   - Layout: Multi-column adaptive grid, side-by-side library and details, cinema-scale media canvas.
3. **Tabletop Mode (Partially Open ~75° to 120°)**:
   - Trigger: `UIHinge.Status == .partiallyOpen` or horizontal orientation with bottom control shelf.
   - Layout:
     - Top half: Clean video canvas (16:9 / 21:9 letterboxed inside the upper display half).
     - Bottom half: Interactive control deck (scrubber, audio/subtitle selectors, chapter markers, playback controls).
