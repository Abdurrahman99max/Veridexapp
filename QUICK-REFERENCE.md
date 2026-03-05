# Veridex Design System - Quick Reference

**One-page cheat sheet for daily use**

---

## 🎨 Brand Colors

```
Navy Blue:      #08307f  →  bg-vx-navy
Spring Green:   #0be149  →  bg-vx-green
White:          #ffffff  →  bg-vx-white
```

---

## 🎨 Common UI Colors

```
Background:     #ffffff  →  bg-background
Text:           #0d1825  →  text-foreground
Border:         #e2e6ed  →  border-border
Muted:          #f0f2f6  →  bg-muted
```

---

## 📝 Typography

```tsx
// Headings
<h1>  32px, weight 500  (automatically styled)
<h2>  24px, weight 500
<h3>  20px, weight 500
<h4>  16px, weight 500

// Body
<p>   16px, weight 400

// Small
14px  →  text-sm
12px  →  text-xs
```

---

## 📐 Spacing Scale

```
4px   →  p-1   gap-1
8px   →  p-2   gap-2
12px  →  p-3   gap-3
16px  →  p-4   gap-4  ← Most common
24px  →  p-6   gap-6
32px  →  p-8   gap-8
48px  →  p-12  gap-12
```

---

## 🔘 Border Radius

```
4px   →  rounded-sm
6px   →  rounded-md
8px   →  rounded-lg   ← Cards, buttons
12px  →  rounded-xl   ← Cards
Full  →  rounded-full ← Badges, avatars
```

---

## 🏷️ Status Colors

```tsx
Verified:  bg-[#0be149]  text-[#07a334]  ← Success
Pending:   bg-amber-100  text-amber-700   ← Warning
Rejected:  bg-red-100    text-red-700     ← Error
Info:      bg-blue-100   text-blue-700    ← Information
```

---

## 🖼️ Logo Components

```tsx
import { VxLogo, VxMark, VxWordmark } from './components/design-system/VxLogo';

// Full logo with background
<VxLogo variant="navy" size="lg" />
<VxLogo variant="green" size="md" />
<VxLogo variant="white" size="sm" />

// Icon only (for favicons, apps)
<VxMark variant="navy" size={48} />

// Horizontal wordmark (for navigation)
<VxWordmark color="navy" size="md" />
```

---

## 🎯 Common Patterns

### Button
```tsx
<button className="px-5 py-2.5 rounded-lg bg-vx-navy text-white hover:bg-vx-navy-dark">
  Action
</button>
```

### Card
```tsx
<div className="bg-white rounded-xl border border-border p-6">
  Card content
</div>
```

### Input
```tsx
<input className="w-full px-4 py-2.5 rounded-lg border border-border bg-input-background focus:ring-2 focus:ring-vx-green" />
```

### Badge
```tsx
<span className="px-2.5 py-1 rounded-full text-xs font-semibold bg-vx-green-light text-vx-green-dark">
  Verified
</span>
```

---

## 📱 Layout

```tsx
// Page container
<div className="min-h-screen bg-background p-6">
  ...
</div>

// Card grid
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  <Card />
  <Card />
  <Card />
</div>

// Flex layout
<div className="flex items-center gap-4">
  <Avatar />
  <Content />
</div>
```

---

## 🎨 Greys (Light to Dark)

```
#f8f9fb  →  bg-vx-grey-50   ← Page background
#f0f2f6  →  bg-vx-grey-100  ← Card background alt
#e2e6ed  →  bg-vx-grey-200  ← Borders
#9aaabb  →  text-vx-grey-400 ← Placeholder text
#6b7f94  →  text-vx-grey-500 ← Secondary text
#4a5d70  →  text-vx-grey-600 ← Body text
#0d1825  →  text-vx-grey-900 ← Heading text
```

---

## 🔍 Design Tokens Path

**In code:**
```tsx
className="bg-vx-green"
style={{ color: 'var(--vx-navy)' }}
```

**In Figma:**
```
Fill → Variable → color/brand/green
Font size → Variable → typography/font-size/base
Gap → Variable → spacing/4
```

---

## 📁 Important Files

```
/design-tokens.json              ← Edit this for token changes
/src/styles/theme.css            ← CSS output (don't edit directly)
/FIGMA-SETUP-GUIDE.md           ← 5-min Figma setup
/src/app/components/design-system/VxLogo.tsx  ← Logo component
```

---

## ⚡ Quick Commands

### Copy design tokens to clipboard
```bash
cat design-tokens.json | pbcopy
```

### Validate JSON
```bash
cat design-tokens.json | jq .
```

### Check theme.css
```bash
cat src/styles/theme.css | grep "vx-"
```

---

## 🎯 Common Tailwind Classes

```
Text colors:
  text-vx-navy
  text-vx-green
  text-vx-grey-500

Backgrounds:
  bg-vx-navy
  bg-vx-green
  bg-background
  bg-muted

Borders:
  border-border
  border-vx-navy
  rounded-lg

Focus states:
  focus:ring-2
  focus:ring-vx-green
  focus:outline-none

Hover states:
  hover:bg-vx-navy-dark
  hover:scale-105
  transition-all
```

---

## 📊 Elevation (Shadows)

```tsx
// Subtle
className="shadow-sm"

// Card
className="shadow-md"

// Modal
className="shadow-lg"

// Popover
className="shadow-xl"
```

---

## 🎨 Status Badges Quick Copy

```tsx
// Verified
<span className="px-2.5 py-1 rounded-full text-xs font-semibold bg-[#d4fce3] text-[#07a334]">
  Verified
</span>

// Pending
<span className="px-2.5 py-1 rounded-full text-xs font-semibold bg-amber-50 text-amber-700">
  Pending
</span>

// Rejected
<span className="px-2.5 py-1 rounded-full text-xs font-semibold bg-red-50 text-red-700">
  Rejected
</span>
```

---

## 🔗 Links

- **Figma Setup:** `/FIGMA-SETUP-GUIDE.md`
- **Token Docs:** `/README-DESIGN-TOKENS.md`
- **Full Guide:** `/DESIGN-SYSTEM-SYNC.md`
- **Summary:** `/DESIGN-SYSTEM-SUMMARY.md`
- **Design System Page:** Run app → view showcase

---

**Bookmark this file for quick reference!** 📌
