# jekyll-theme-phosphor

A minimal Jekyll theme that renders pages as if they were on the screen
of a P1 green-phosphor VT100. Pixel font (VT323), 80-column body,
soft text-shadow glow, faint CRT scanline overlay, monochrome syntax
highlighting.

Designed to be consumed as a **remote theme** from GitHub Pages — no
gem, no Gemfile required on the consumer side.

## Use it on GitHub Pages

In your site's `_config.yml`:

```yaml
remote_theme: ajbonner/jekyll-theme-phosphor@v0.1.0
plugins:
  - jekyll-remote-theme
```

That is the entire integration. Your existing Markdown content,
front-matter `layout: default`, and any other supported plugins keep
working.

## Customising the palette

Every visual constant is a CSS custom property declared on `:root` in
`_sass/jekyll-theme-phosphor.scss`. To switch from P1 green to P3
amber without forking the theme, shadow `assets/css/style.scss` in
your own repo:

```scss
---
---
@import "jekyll-theme-phosphor";

:root {
  --fg: #ffb000;
  --fg-dim: #aa6800;
  --fg-bright: #ffd070;
  --glow: 0 0 4px rgba(255, 176, 0, 0.55), 0 0 12px rgba(255, 176, 0, 0.25);
  --scanline-rgba: rgba(0, 0, 0, 0.18);
}
```

Same pattern for P4 white phosphor, or to disable the scanline
overlay (`--scanline-rgba: transparent`).

## What the theme provides

- `_layouts/default.html` — the only layout. Banner across the top,
  blinking-caret shell prompt across the bottom, 80ch content column
  in the middle.
- `_sass/jekyll-theme-phosphor.scss` — every visual rule.
- `assets/css/style.scss` — two-line entry point that consumers can
  shadow.

No `_includes/` are required; the layout is small enough to keep
inline.

## Local preview

```sh
gem install bundler github-pages
github-pages serve
```

Or for fast iteration:

```sh
jekyll serve
```

## License

MIT — see [`LICENSE`](LICENSE).
