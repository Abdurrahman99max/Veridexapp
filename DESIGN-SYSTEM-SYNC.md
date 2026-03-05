# Veridex Design System → Figma Sync Guide

This guide explains how to maintain **single source of truth** for the Veridex design system across both the web application and Figma.

---

## 📋 Overview

The design system is defined in **`design-tokens.json`**, which contains all design decisions as structured data:

- **Colors** (brand, semantic, status, charts)
- **Typography** (sizes, weights, line heights)
- **Spacing** (layout scale)
- **Border radius** (component roundness)
- **Shadows** (elevation system)
- **Opacity** (UI states)

This file generates:
- ✅ **CSS variables** → `/src/styles/theme.css` (for web)
- ✅ **Figma Variables** → Import into Figma (for design)

---

## 🔄 Workflow Options

### **Option 1: Tokens Studio Plugin** (Recommended)

**Best for:** Bi-directional sync, automatic updates, team collaboration

#### Setup Steps:

1. **Install Tokens Studio in Figma**
   - Open Figma → Plugins → Browse → Search "Tokens Studio for Figma"
   - Install and open the plugin

2. **Connect to JSON file**
   - In Tokens Studio panel → Settings → Add New
   - **Method A:** GitHub Sync (recommended for teams)
     - Connect your repo
     - Point to `/design-tokens.json`
     - Set up automatic sync
   
   - **Method B:** Manual JSON Import
     - Copy contents of `design-tokens.json`
     - Paste into Tokens Studio → Import

3. **Apply tokens to Figma**
   - Tokens Studio will create Figma Variables automatically
   - Map tokens to your design components

4. **Update workflow**
   ```
   1. Edit design-tokens.json
   2. Push to GitHub (if using sync)
   3. Tokens Studio auto-updates Figma
   4. Regenerate theme.css (see below)
   ```

**Documentation:** https://docs.tokens.studio/

---

### **Option 2: Figma Variables Import (Native)**

**Best for:** Simple setup, no plugins

#### Setup Steps:

1. **Convert tokens to Figma format**
   - Tokens need to be in Figma's native format
   - Use this script or online converter

2. **Import to Figma**
   - Right-click Figma canvas → Variables → Import
   - Upload converted JSON
   - Figma creates Variables automatically

3. **Manual sync required**
   - Update `design-tokens.json` → manually re-import to Figma

---

### **Option 3: Style Dictionary** (Advanced)

**Best for:** Multi-platform output, automated builds

#### Setup:

```bash
npm install style-dictionary
```

Create `style-dictionary.config.js`:

```js
module.exports = {
  source: ['design-tokens.json'],
  platforms: {
    css: {
      transformGroup: 'css',
      buildPath: 'src/styles/',
      files: [{
        destination: 'tokens.css',
        format: 'css/variables'
      }]
    },
    figma: {
      transformGroup: 'js',
      buildPath: 'design/',
      files: [{
        destination: 'figma-tokens.json',
        format: 'json/flat'
      }]
    }
  }
};
```

Run build:
```bash
npx style-dictionary build
```

Import `figma-tokens.json` to Figma using Tokens Studio.

---

## 🎨 Using Tokens in Figma

Once imported, tokens become **Figma Variables**:

### Color Tokens
```
color/brand/green       → #0be149
color/brand/navy        → #08307f
color/semantic/primary  → #08307f
```

**Usage in Figma:**
- Select layer → Fill → Select variable → `color/brand/green`

### Typography Tokens
```
typography/font-size/base → 16px
typography/font-size/xl   → 20px
typography/font-weight/medium → 500
```

**Usage in Figma:**
- Text layer → Font size → Select variable → `typography/font-size/xl`

### Spacing Tokens
```
spacing/4  → 16px
spacing/8  → 32px
spacing/12 → 48px
```

**Usage in Figma:**
- Auto Layout → Gap → Select variable → `spacing/4`

---

## 🔧 Maintaining the System

### When to Update Tokens

**Update `design-tokens.json` when:**
- Adding new brand colors
- Changing typography scale
- Adjusting spacing values
- Creating new semantic tokens

### Update Process:

1. **Edit `design-tokens.json`**
   ```json
   "color": {
     "brand": {
       "new-color": {
         "$type": "color",
         "$value": "#ff5733"
       }
     }
   }
   ```

2. **Regenerate CSS (if needed)**
   - If using Style Dictionary, run build
   - Otherwise, manually update `/src/styles/theme.css`

3. **Sync to Figma**
   - Tokens Studio: Auto-sync or click "Pull from GitHub"
   - Native Figma: Re-import JSON file

4. **Update components**
   - Web: Use new token in code (`text-vx-new-color`)
   - Figma: Apply new variable to layers

---

## 📐 Design System Structure

### Current Token Categories:

| Category | Tokens | Usage |
|----------|--------|-------|
| **Brand Colors** | `color.brand.*` | Logo, primary CTAs, brand moments |
| **Grey Scale** | `color.grey.*` | Backgrounds, borders, text hierarchy |
| **Status Colors** | `color.status.*` | Verification badges, alerts, feedback |
| **Semantic Colors** | `color.semantic.*` | UI components (buttons, cards, inputs) |
| **Typography** | `typography.*` | All text sizing, weights, spacing |
| **Spacing** | `spacing.*` | Layout gaps, padding, margins |
| **Radius** | `radius.*` | Component roundness (cards, buttons) |
| **Shadows** | `shadow.*` | Elevation and depth |

---

## 🚀 Quick Start Commands

### For Designers (Figma)

1. Install Tokens Studio plugin
2. Import `design-tokens.json`
3. Use variables in designs
4. Export updated designs to Dev team

### For Developers (Web)

1. Edit `design-tokens.json` for system changes
2. Use CSS variables: `var(--vx-green)` or Tailwind: `bg-vx-green`
3. Commit changes to repo
4. Figma auto-syncs (if using Tokens Studio GitHub sync)

---

## 🎯 Example: Adding a New Color

### 1. Add to `design-tokens.json`:
```json
"color": {
  "brand": {
    "blue-accent": {
      "$type": "color",
      "$value": "#2563eb",
      "$description": "Secondary accent for links and highlights"
    }
  }
}
```

### 2. Add to CSS (manual or via build):
```css
:root {
  --vx-blue-accent: #2563eb;
}

@theme inline {
  --color-vx-blue-accent: var(--vx-blue-accent);
}
```

### 3. Sync to Figma:
- Tokens Studio: Pull from GitHub or re-import JSON
- Variable appears as `color/brand/blue-accent`

### 4. Use in code:
```tsx
<div className="bg-vx-blue-accent">
  Highlighted content
</div>
```

### 5. Use in Figma:
- Select layer → Fill → Variable → `color/brand/blue-accent`

---

## 📚 Resources

- **Design Tokens Spec:** https://tr.designtokens.org/
- **Tokens Studio Docs:** https://docs.tokens.studio/
- **Style Dictionary:** https://amzn.github.io/style-dictionary/
- **Figma Variables:** https://help.figma.com/hc/en-us/articles/15339657135383

---

## ⚠️ Important Notes

1. **Never edit theme.css directly** — always update `design-tokens.json` first
2. **Version control tokens** — commit `design-tokens.json` to Git
3. **Document changes** — add descriptions to new tokens
4. **Test both platforms** — verify changes work in web AND Figma
5. **Communicate updates** — notify team when tokens change

---

## 🔄 Current Sync Status

**Design Tokens Version:** 1.0.0  
**Last Updated:** Initial setup  
**Figma File:** [Add link to your Figma file]  
**Sync Method:** [To be configured: Tokens Studio or Native]

---

## 🤝 Team Workflow

### Designer's Responsibility:
- Use Figma Variables for all designs
- Request new tokens via design-tokens.json updates
- Export updated designs with token annotations

### Developer's Responsibility:
- Maintain design-tokens.json as source of truth
- Sync tokens to Figma when updated
- Use CSS variables/Tailwind classes in code
- Review token usage in PRs

---

**Questions?** Check the Resources section or create an issue in the repo.
