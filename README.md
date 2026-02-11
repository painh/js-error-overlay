# js-error-overlay

Browser JS error/warning overlay for development. Catches errors and warnings, shows them in a floating panel.

![badge](https://img.shields.io/badge/zero_dependencies-true-green)

## What it catches

- `window.onerror` (runtime errors)
- `unhandledrejection` (unhandled promise rejections)
- `console.warn` (warnings)

## Install

### Git submodule

```bash
git submodule add https://github.com/painh/js-error-overlay.git lib/js-error-overlay
```

### Copy

Or just copy `src/index.ts` into your project.

## Usage

```ts
import { install } from './lib/js-error-overlay/src';

// Call once at startup (e.g. only in dev mode)
install();
```

Typical pattern with a dev flag:

```ts
if (isDev) {
  install();
}
```

## Features

- Red badge (bottom-right) shows error count, click to open
- Badge color: red if errors exist, orange if warnings only
- Fullscreen overlay with scrollable error/warning list
- Each entry shows: message, source location, stack trace, timestamp
- **Copy** per entry or **Copy All**
- **Clear** to reset
- **Close** or press `Esc`
- Errors: red left border
- Warnings: yellow left border

## CSS prefix

All CSS classes are prefixed with `jeo-` to avoid collisions.

## License

MIT
