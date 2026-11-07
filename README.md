# Diwali Rangoli Like

A festive take on the "like" button. Tap the heart and it blooms into a spinning rangoli mandala, then washes back into a heart filled with slowly flowing rangoli colours. Built for Diwali, inspired by X's seasonal like animations.

Single file. Plain HTML, CSS and JavaScript. No dependencies, no build step.

## The animation

1. **Pop.** The outline heart zooms up and out.
2. **Bloom.** A mandala springs in, spins slowly, and its petals pop in one by one. Petal confetti flies outward.
3. **Backwash.** The mandala recedes into the heart like a wave pulling back.
4. **Settle.** A gradient heart rises out of it with a soft spring, and a rainbow ring and sparkles release.
5. **Flow.** Yellow, orange, magenta, purple and teal drift continuously inside the heart.

Unliking reverses the heart back to its outline. The count rolls digit by digit, up on like and down on unlike.

## Features

- Spring physics modelled on SwiftUI's `.spring(response:dampingFraction:)`, converted to CSS `linear()` easing
- Per-digit rolling counter with blur, similar to SwiftUI's `.numericText()`
- iOS-style press squish and a small haptic tick on supported devices
- Colours drawn from the mandala's own palette, with a live drifting-blob gradient
- Respects `prefers-reduced-motion` (skips the sequence and keeps the heart still)
- Keyboard accessible, with `aria-pressed` and a live-region count
- Demo controls for **Slow-mo** (4x) and **Zoom**, to inspect the motion

## Usage

Open `index.html` in a browser. That's it.

To use it in your own project, copy the `.like` button markup, the CSS, and the script. The starting count is the `n` variable in the script (currently `554`, which becomes `555` on like).

## Customising

| What | Where |
| --- | --- |
| Starting count | `n = 554` in the script |
| Icon size | `--icon` CSS variable |
| Like colour (count and hover) | `--pink` CSS variable (currently X's `#f91880`) |
| Mandala design and colours | `ring_(...)` calls in the script |
| Heart colours | `.mesh` and `.b1`–`.b5` blob styles |
| Timing | `playLike()` in the script (`T` marks when the backwash starts) |

## Font

The count prefers Chirp, X's typeface, if it is installed on the device or placed at `fonts/chirp-regular-web.woff2`. Chirp is proprietary and is **not** included in this repo. Otherwise it falls back to Public Sans, which is embedded in the file (SIL Open Font License) and is the closest free match to Chirp's numerals.

## Browser support

Works in current Chrome, Edge, Firefox and Safari. Spring easing uses CSS `linear()` (Chrome 113+, Safari 17.2+, Firefox 112+). Older browsers get a close cubic-bezier approximation.

## Notes

This is a personal project and is not affiliated with or endorsed by X Corp. "X", "Twitter" and "Chirp" belong to their respective owners.

## License

Add a license of your choice (MIT is a common default for small demos). Public Sans is licensed separately under the SIL Open Font License 1.1.
