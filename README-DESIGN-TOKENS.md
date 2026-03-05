# Veridex Design Tokens

This directory contains the **design system source of truth** for the Veridex platform.

---

## 📁 Files

### `/design-tokens.json`
**The single source of truth** for all design decisions.

Contains:
- ✅ Brand colors (Navy Blue, Spring Green, White)
- ✅ Greyscale palette (50-900)
- ✅ Status colors (verified, pending, rejected, info)
- ✅ Semantic UI colors (light & dark modes)
- ✅ Typography (font sizes, weights, line heights)
- ✅ Spacing scale (4px increments)
- ✅ Border radius values
- ✅ Shadow system
- ✅ Opacity scale

**Format:** W3C Design Tokens Community Group specification  
**Spec:** https://tr.designtokens.org/format/

---

## 🔄 How It Works

```
design-tokens.json (source of truth)
        ↓
        ├─► /src/styles/theme.css (manual sync for now)
        └─► Figma Variables (via Tokens Studio plugin)
```

---

## 🎨 Using Tokens

### In Code (Web App)

**CSS Variables:**
```css
.element {
  background: var(--vx-green);
  color: var(--vx-navy);
  padding: var(--spacing-4); /* 16px */
}
```

**Tailwind Classes:**
```tsx
<div className="bg-vx-green text-vx-navy p-4">
  Verified student
</div>
```

**Direct Token Reference:**
```tsx
<div style={{ color: '#0be149' }}>
  Spring Green text
</div>
```

### In Figma

1. **Install Tokens Studio plugin**
2. **Import `design-tokens.json`**
3. **Use as Figma Variables:**
   - Fill → Variable → `color/brand/green`
   - Font size → Variable → `typography/font-size/base`
   - Auto Layout gap → Variable → `spacing/4`

---

## 📝 Token Structure

### Color Tokens

```json
{
  "color": {
    "brand": {
      "green": { "$value": "#0be149" },
      "navy": { "$value": "#08307f" },
      "white": { "$value": "#ffffff" }
    },
    "grey": {
      "50": { "$value": "#f8f9fb" },
      ...
      "900": { "$value": "#0d1825" }
    },
    "status": {
      "verified": { "$value": "#0be149" },
      "pending": { "$value": "#f59e0b" },
      "rejected": { "$value": "#d4183d" }
    },
    "semantic": {
      "primary": { "$value": "#08307f" },
      "accent": { "$value": "#0be149" },
      ...
    }
  }
}
```

### Typography Tokens

```json
{
  "typography": {
    "font-size": {
      "xs": { "$value": "12px" },
      "sm": { "$value": "14px" },
      "base": { "$value": "16px" },
      "xl": { "$value": "20px" }
    },
    "font-weight": {
      "normal": { "$value": 400 },
      "medium": { "$value": 500 },
      "bold": { "$value": 700 }
    }
  }
}
```

### Spacing Tokens

```json
{
  "spacing": {
    "1": { "$value": "4px" },
    "2": { "$value": "8px" },
    "4": { "$value": "16px" },
    "8": { "$value": "32px" }
  }
}
```

---

## ✏️ Updating Tokens

### Step 1: Edit `design-tokens.json`

```json
{
  "color": {
    "brand": {
      "new-color": {
        "$type": "color",
        "$value": "#ff5733",
        "$description": "New brand accent"
      }
    }
  }
}
```

### Step 2: Update `theme.css`

```css
:root {
  --vx-new-color: #ff5733;
}

@theme inline {
  --color-vx-new-color: var(--vx-new-color);
}
```

### Step 3: Sync to Figma

**If using Tokens Studio GitHub sync:**
- Push to GitHub → Figma auto-updates

**If using manual import:**
- Copy JSON → Tokens Studio → Import

### Step 4: Use in code

```tsx
<div className="bg-vx-new-color">
  New color applied!
</div>
```

---

## 🚀 Quick Setup

### For Designers (Figma)

1. **Install Tokens Studio plugin**  
   Figma → Plugins → Browse → "Tokens Studio for Figma"

2. **Import tokens**  
   Tokens Studio → Settings → Add New → Import JSON  
   → Paste contents of `design-tokens.json`

3. **Create Variables**  
   Tokens Studio → Create Variables → All tokens

4. **Use in designs**  
   Select layer → Fill → Variable → `color/brand/green`

**Detailed guide:** `/FIGMA-SETUP-GUIDE.md`

### For Developers (Web)

1. **Reference tokens in code:**
   ```tsx
   className="bg-vx-green text-vx-navy"
   ```

2. **Add new tokens:**
   - Edit `design-tokens.json`
   - Update `theme.css`
   - Commit & push

3. **Figma syncs automatically** (if using GitHub sync)

---

## 📚 Documentation

| File | Purpose |
|------|---------|
| `design-tokens.json` | Token definitions (source of truth) |
| `DESIGN-SYSTEM-SYNC.md` | Full sync workflow documentation |
| `FIGMA-SETUP-GUIDE.md` | Quick Figma setup instructions |
| `/src/styles/theme.css` | Generated CSS variables |

---

## 🎯 Token Categories

| Category | Count | Purpose |
|----------|-------|---------|
| **Brand Colors** | 7 | Logo, primary CTAs, brand moments |
| **Grey Scale** | 9 | Backgrounds, borders, text hierarchy |
| **Status Colors** | 4 | Verification badges, alerts, feedback |
| **Semantic Colors** | 14+ | UI components (buttons, cards, inputs) |
| **Typography** | 20+ | Text sizing, weights, spacing |
| **Spacing** | 13 | Layout gaps, padding, margins |
| **Radius** | 7 | Component roundness |
| **Shadows** | 4 | Elevation system |
| **Opacity** | 11 | UI states, overlays |

---

## ⚠️ Important Rules

1. ✅ **Always edit `design-tokens.json` first**  
   Never manually edit theme.css or Figma values directly

2. ✅ **Document all changes**  
   Add `$description` to new tokens explaining their purpose

3. ✅ **Test in both platforms**  
   Verify changes work in web AND Figma before merging

4. ✅ **Version control**  
   Commit token changes to Git with descriptive messages

5. ✅ **Communicate updates**  
   Notify team when tokens change (affects designers & devs)

---

## 🔍 Token Validation

**Check token validity:**
```bash
# Validate JSON structure
cat design-tokens.json | jq .
```

**Online validator:**
https://jsonlint.com/

**Check compliance with W3C spec:**
https://tr.designtokens.org/format/validator

---

## 🤝 Workflow Summary

### Designer Workflow
1. Use Figma Variables in designs
2. Request new tokens via Slack/GitHub issue
3. Developer adds token to `design-tokens.json`
4. Designer pulls updated tokens into Figma
5. Designs stay in sync with code ✅

### Developer Workflow
1. Edit `design-tokens.json` for new values
2. Update `theme.css` (manual for now, automated later)
3. Commit and push changes
4. Tokens auto-sync to Figma (if using GitHub sync)
5. Code and designs stay in sync ✅

---

## 📞 Questions?

- **Token format questions:** See W3C spec at https://tr.designtokens.org/
- **Figma sync issues:** See `FIGMA-SETUP-GUIDE.md`
- **New token requests:** Create issue or ask in #design channel
- **Technical questions:** Ask dev team

---

**Version:** 1.0.0  
**Last Updated:** March 2026  
**Maintained By:** Veridex Platform Team
