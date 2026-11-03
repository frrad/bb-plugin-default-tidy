# Default Tidy for BB

The default BB palette with a tidier sidebar, packaged as a selectable theme.

```sh
bb plugin install git:https://github.com/frrad/bb-plugin-default-tidy.git@main
bb theme set plugin:default-tidy:default-tidy
```

Requires BB 0.48 or later with a compatible Plugin SDK (see package.json).
Installing adds the theme to Settings → Appearance; selecting it activates it.
It inherits BB’s default light and dark colors.

The theme hides the top New thread button, keeps expanded section headings
open, increases heading size, indents thread rows, and tightens section gaps.
Custom sections named with a leading `- ` become divider labels with a hairline:

```sh
bb thread section create -- "- work"
```

Keep divider sections empty: their bodies are hidden. Collapsed sections retain
their toggle so they can be reopened. Per-thread child toggles remain available.

These layout rules target BB’s internal DOM and may need adjustment after BB
updates. This plugin does not sync shortcuts or other preferences; those remain
in [the settings repo](https://github.com/frrad/bb).

## Update or disable

```sh
bb plugin update default-tidy
bb theme reset
```

Switching themes removes the layout changes. Disable or remove the plugin only
after switching away from its theme.

## Development

Edit `themes/default-tidy/theme.css`, then run:

```sh
npm ci
npm run typecheck
bb plugin build
```

There is no frontend bundle, runtime dependency, CLI command, or background service.
