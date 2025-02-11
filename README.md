# Expo Camera: Unexpected Photo Capture Outside Preview Area

This repository demonstrates a bug in Expo's Camera API where photos are captured even when taps occur outside the preview area, interfering with custom UI controls.  The bug is especially apparent when using custom buttons or overlays. The solution focuses on precisely detecting taps within the camera preview boundaries to prevent this unwanted behavior.

## Bug Description:

When using custom UI elements (buttons, etc.) overlaid on top of the Expo Camera preview, taps anywhere on the screen might trigger a photo capture, rather than only when the user interacts with designated capture elements. This behavior overrides the expected functionality of custom controls and results in unintended photo captures.

## Solution:

The solution presented involves accurately identifying taps within the camera preview's boundaries. The code uses the native event coordinates to check if a tap occurred within the preview area before triggering the capture action.