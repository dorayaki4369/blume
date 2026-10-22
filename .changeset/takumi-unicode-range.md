---
"blume": patch
---

Update takumi-js to 2.17 and read Google Fonts subsets the way it now returns them. `@takumi-rs/helpers` 2.16.0 renamed a subset's `ranges` to `unicodeRange`, made `name` the family, and dropped `subsetOf`; Blume still read the old fields, so a project whose lock file resolved Blume's `^2.13.7` range to 2.16 or newer failed every build in `renderOgImage` with `TypeError: Cannot read properties of undefined (reading 'length')`, and the script fallbacks could no longer tell families apart. Blume now requires takumi-js 2.17.1 or newer and reads the new fields. Since Takumi 2.17 the built-in font draws the vertical tab and the line and paragraph separators as missing glyphs, and `Ÿ` once any other font is registered, so a card holding one of them now loads a fallback font for it instead of shipping tofu.
