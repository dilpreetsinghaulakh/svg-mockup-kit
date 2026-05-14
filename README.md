# svg-mockup-kit

SVG + `foreignObject`-based device mockup components for React. Drop any content into a pixel-perfect MacBook (and more devices soon) with zero dependencies beyond React itself.

## Install

```bash
npm install svg-mockup-kit
# or
pnpm add svg-mockup-kit
```

## Usage

```tsx
import { MacbookMockup } from "svg-mockup-kit";

export default function Demo() {
  return (
    <div className="w-full max-w-3xl mx-auto">
      <MacbookMockup>
        <img
          src="/your-screenshot.png"
          style={{ width: "100%", height: "100%", objectFit: "cover" }}
        />
      </MacbookMockup>
    </div>
  );
}
```

### With a live iframe

```tsx
<MacbookMockup className="w-full">
  <iframe
    src="https://example.com"
    style={{ width: "100%", height: "100%", border: "none" }}
  />
</MacbookMockup>
```

### With a custom className / style

```tsx
<MacbookMockup className="w-2/3 shadow-2xl" style={{ maxWidth: 800 }}>
  <YourComponent />
</MacbookMockup>
```

## Props — `MacbookMockup`

| Prop        | Type                  | Required | Description                                 |
|-------------|-----------------------|----------|---------------------------------------------|
| `children`  | `React.ReactNode`     | ✅       | Content rendered inside the screen area     |
| `className` | `string`              | —        | CSS class applied to the root `<svg>`       |
| `style`     | `React.CSSProperties` | —        | Inline style applied to the root `<svg>`    |

### Screen viewport

The SVG `viewBox` is **1216 × 735**. The usable screen area is **967 × 628** (starts at x=124.5, y=18.3 inside the SVG). Content is clipped to the rounded screen shape automatically.

## Building

```bash
pnpm install
pnpm build      # outputs to dist/
pnpm dev        # watch mode
```

## Publishing to npm

1. Set your package name in `package.json` → `"name"` (must be unique on npm).
2. `npm login`
3. `npm publish --access public`

To use a scoped name (e.g. `@yourname/svg-mockup-kit`):
```bash
npm publish --access public
```

## Roadmap

- [ ] iPhone mockup
- [ ] iPad mockup
- [ ] Browser window mockup
- [ ] `screenshotUrl` prop (auto-fills screen with an image)

## License

MIT
