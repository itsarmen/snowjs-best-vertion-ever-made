# snowjs-best-vertion-ever-made

**Let it snow** ❄️

The best-ever snow effect for the web. Drop one file on a page and it snows.

This is **DHTML Snowstorm** by [Scott Schiller](http://schillmania.com/projects/snowstorm/),
a tiny, dependency-free JavaScript snow effect that has been "making it snow on the
internets since 2003".

- **File:** `snow.js`
- **License:** BSD — see <http://schillmania.com/projects/snowstorm/license.txt>
- **Original project:** <http://schillmania.com/projects/snowstorm/>

---

## Quick start

1. Copy `snow.js` next to your page (or drop it in your `assets/js` folder).
2. Add one line before `</body>`:

```html
<script src="snow.js" type="text/javascript"></script>
```

That's it — the snow starts automatically on page load.

See [`example.html`](./example.html) for a full, ready-to-open demo.

---

## Customizing

The script exposes a global `snowStorm` object. To change settings, set the
properties in a `<script>` that runs **after** `snow.js` is loaded but **before**
the window `load` event fires (the effect auto-starts on `load`):

```html
<script src="snow.js" type="text/javascript"></script>
<script type="text/javascript">
    snowStorm.snowColor = '#eef6ff';     // flake color
    snowStorm.flakesMax = 128;           // total flakes created
    snowStorm.flakesMaxActive = 64;      // max falling at the same time
    snowStorm.animationInterval = 33;    // ms/frame (lower = smoother, more CPU)
    snowStorm.snowCharacter = '❄';       // flake glyph
</script>
```

If you load the script *after* the page has already loaded, call the start hook
manually:

```js
snowStorm.start();
```

---

## Options

| Property | Default | Description |
|---|---|---|
| `autoStart` | `true` | Start the snow automatically on window load. |
| `excludeMobile` | `true` | Skip running on mobile devices (CPU/battery friendly). |
| `flakesMax` | `128` | Maximum number of snowflakes created. |
| `flakesMaxActive` | `64` | Maximum number of flakes falling at once. |
| `animationInterval` | `50` | Target milliseconds per frame. `20` = fast + smooth, `50` = lighter on CPU. |
| `useGPU` | `true` | Use transform-based hardware acceleration. |
| `className` | `null` | Extra CSS class applied to every flake element. |
| `flakeBottom` | `null` | Y-axis limit for the snow; `0`/`null` = full screen. |
| `followMouse` | `false` | Wind reacts to mouse movement. |
| `snowColor` | `#ddd` | Flake color. |
| `snowCharacter` | `*` | The glyph used for a flake (`❄`, `&bull;`, `&middot;` …). |
| `snowStick` | `true` | Snow collects at the bottom. |
| `targetElement` | `null` | Element (id string or DOM node) to snow inside; `null` = `document.body`. |
| `useMeltEffect` | `true` | Flakes melt/fade when recycled. |
| `useTwinkleEffect` | `false` | Flakes randomly flicker in/out. |
| `usePositionFixed` | `false` | Snow stays put while scrolling (may increase CPU). |
| `usePixelPosition` | `false` | Use pixel (vs. percent) positioning. |
| `freezeOnBlur` | `true` | Only snow while the window is focused. |
| `flakeLeftOffset` / `flakeRightOffset` | `0` | Left/right gutter margins. |
| `flakeWidth` / `flakeHeight` | `28` / `28` | Reserved size per flake. |
| `vMaxX` / `vMaxY` | `5` / `4` | Max horizontal / vertical velocity. |
| `zIndex` | `900` | CSS stacking order for flakes. |

---

## API

```js
snowStorm.start();        // start (or restart) the effect
snowStorm.stop();         // stop and hide flakes
snowStorm.freeze();       // pause animation
snowStorm.resume();       // resume animation
snowStorm.toggleSnow();   // toggle on/off
snowStorm.active;         // currently active?
```

---

## Browser support

Works in all modern browsers. GPU acceleration is used when available; on very old
browsers it falls back to `setTimeout`-based animation automatically.

---

## License

BSD License. Copyright (c) 2007, Scott Schiller. All rights reserved.
See <http://schillmania.com/projects/snowstorm/license.txt>.
