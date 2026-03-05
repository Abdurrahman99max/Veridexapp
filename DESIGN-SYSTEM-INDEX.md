# Veridex Design System - Documentation Index

**Complete guide to the Veridex design system and Figma sync workflow**

---

## 📚 Documentation Structure

### 🎯 Start Here

| Document | Purpose | Read Time |
|----------|---------|-----------|
| **DESIGN-SYSTEM-SUMMARY.md** | Overview of what was built | 5 min |
| **FIGMA-SETUP-GUIDE.md** | Quick Figma setup instructions | 5 min |
| **QUICK-REFERENCE.md** | Daily use cheat sheet | 2 min |

### 📖 Deep Dives

| Document | Purpose | Read Time |
|----------|---------|-----------|
| **DESIGN-SYSTEM-SYNC.md** | Complete sync workflow | 15 min |
| **README-DESIGN-TOKENS.md** | Token structure and usage | 10 min |

### 📁 Source Files

| File | Purpose |
|------|---------|
| **design-tokens.json** | Single source of truth for design decisions |
| **/src/styles/theme.css** | CSS implementation of tokens |
| **/src/app/components/design-system/VxLogo.tsx** | Logo component |
| **/src/app/components/design-system/DesignSystemPage.tsx** | Living documentation |

---

## 🚀 Quick Start Paths

### For Designers (New to Project)

1. **Read:** `FIGMA-SETUP-GUIDE.md` (5 min)
2. **Do:** Install Tokens Studio plugin
3. **Do:** Import `design-tokens.json` to Figma
4. **Do:** Create Figma Variables
5. **Reference:** `QUICK-REFERENCE.md` for daily use
6. **Bookmark:** `design-tokens.json` for color values

**Time to productive:** ~15 minutes

---

### For Developers (New to Project)

1. **Read:** `DESIGN-SYSTEM-SUMMARY.md` (5 min)
2. **Explore:** `design-tokens.json` structure
3. **Review:** `/src/styles/theme.css` CSS output
4. **Test:** VxLogo component variants
5. **Reference:** `QUICK-REFERENCE.md` for Tailwind classes
6. **Build:** Use design system page as component library

**Time to productive:** ~20 minutes

---

### For Product/Stakeholders

1. **Read:** `DESIGN-SYSTEM-SUMMARY.md` (5 min)
2. **View:** Design System page in running app
3. **Understand:** Token categories and purpose
4. **Know:** How to request new tokens/components

**Time to productive:** ~10 minutes

---

## 📂 File Tree

```
/
├── design-tokens.json                    ← SOURCE OF TRUTH
├── DESIGN-SYSTEM-SUMMARY.md             ← Start here
├── FIGMA-SETUP-GUIDE.md                 ← 5-min Figma setup
├── DESIGN-SYSTEM-SYNC.md                ← Full workflow
├── README-DESIGN-TOKENS.md              ← Token reference
├── QUICK-REFERENCE.md                   ← Cheat sheet
├── DESIGN-SYSTEM-INDEX.md               ← This file
│
├── /src/
│   ├── /styles/
│   │   ├── theme.css                    ← CSS variables (generated)
│   │   ├── fonts.css                    ← Font imports
│   │   └── tailwind.css                 ← Tailwind config
│   │
│   ├── /app/components/design-system/
│   │   ├── VxLogo.tsx                   ← Logo component
│   │   └── DesignSystemPage.tsx         ← Living documentation
│   │
│   └── /imports/
│       ├── Asset_1.svg                  ← Navy background logo
│       ├── Artboard_6.svg               ← Green background logo
│       ├── Artboard_8.svg               ← White background logo
│       └── Artboard_4.svg               ← Grayscale logo
│
└── /guidelines/
    └── Guidelines.md                     ← Project guidelines
```

---

## 🎯 Common Tasks

### I want to... use the logo in code

**Read:** `QUICK-REFERENCE.md` → "Logo Components" section

```tsx
import { VxLogo } from './components/design-system/VxLogo';
<VxLogo variant="navy" size="lg" />
```

---

### I want to... sync design tokens to Figma

**Read:** `FIGMA-SETUP-GUIDE.md` (entire file, 5 min)

**Steps:**
1. Install Tokens Studio plugin
2. Import `design-tokens.json`
3. Create Variables

---

### I want to... add a new color to the system

**Read:** `README-DESIGN-TOKENS.md` → "Updating Tokens" section

**Steps:**
1. Edit `design-tokens.json`
2. Update `/src/styles/theme.css`
3. Sync to Figma (auto or manual)
4. Use in code/design

---

### I want to... understand the token structure

**Read:** `README-DESIGN-TOKENS.md` → "Token Structure" section

**Categories:**
- Brand colors
- Greyscale
- Status colors
- Semantic UI colors
- Typography
- Spacing
- Radius, shadows, opacity

---

### I want to... see all components in action

**Do:** Run the app → Navigate to Design System page

**Or read:** `DESIGN-SYSTEM-SUMMARY.md` → "Design System in Action"

---

### I want to... maintain design/code consistency

**Read:** `DESIGN-SYSTEM-SYNC.md` (full workflow, 15 min)

**Key principle:** `design-tokens.json` is the single source of truth

---

## 🎨 Design System Overview

### What's Included

✅ **90+ Design Tokens**
- Colors (brand, semantic, status, charts)
- Typography (sizes, weights, spacing)
- Spacing scale (4px increments)
- Border radius
- Shadows
- Opacity

✅ **Logo System**
- VxLogo (4 background variants)
- VxMark (icon/favicon versions)
- VxWordmark (horizontal navigation)

✅ **Component Library**
- Buttons (5 variants)
- Badges (6 variants)
- Forms (inputs, textareas, selects)
- Cards
- Avatars
- Alerts
- Progress bars
- Stats displays

✅ **Documentation**
- Living design system page
- Token reference
- Usage guidelines
- Code examples

---

## 🔄 Sync Workflow Summary

### Design → Code

1. Designer creates in Figma using Variables
2. Developer exports Figma design
3. Developer implements using same tokens
4. Design and code match perfectly ✅

### Code → Design

1. Developer adds token to `design-tokens.json`
2. Developer updates `theme.css`
3. Designer pulls updated tokens in Figma
4. New token available in Figma Variables ✅

**Key:** `design-tokens.json` is always the source of truth

---

## 📖 Documentation by Role

### Designers

**Must Read:**
- `FIGMA-SETUP-GUIDE.md`
- `QUICK-REFERENCE.md`

**Optional:**
- `DESIGN-SYSTEM-SUMMARY.md`
- `README-DESIGN-TOKENS.md`

**Daily Use:**
- `QUICK-REFERENCE.md` (bookmark it!)
- `design-tokens.json` (for exact hex values)

---

### Developers

**Must Read:**
- `DESIGN-SYSTEM-SUMMARY.md`
- `README-DESIGN-TOKENS.md`
- `QUICK-REFERENCE.md`

**Optional:**
- `DESIGN-SYSTEM-SYNC.md`
- `FIGMA-SETUP-GUIDE.md`

**Daily Use:**
- `QUICK-REFERENCE.md` (bookmark it!)
- `/src/styles/theme.css` (available tokens)
- Design System page (component examples)

---

### Product/Stakeholders

**Must Read:**
- `DESIGN-SYSTEM-SUMMARY.md`

**Optional:**
- `DESIGN-SYSTEM-SYNC.md` (understand workflow)

**When Needed:**
- How to request new colors/tokens
- How to propose component additions

---

## 🎓 Learning Path

### Level 1: Basic Understanding (15 min)

1. Read `DESIGN-SYSTEM-SUMMARY.md`
2. Skim `QUICK-REFERENCE.md`
3. View Design System page in app

**You can now:** Use existing components and colors

---

### Level 2: Proficient (45 min)

1. Complete Level 1
2. Read `FIGMA-SETUP-GUIDE.md` OR `README-DESIGN-TOKENS.md`
3. Set up Figma sync OR explore token structure

**You can now:** Design in Figma OR build with tokens

---

### Level 3: Expert (90 min)

1. Complete Level 2
2. Read `DESIGN-SYSTEM-SYNC.md`
3. Practice adding a new token
4. Understand full bidirectional workflow

**You can now:** Maintain and evolve the design system

---

## 🔗 External Resources

### Design Tokens
- **W3C Spec:** https://tr.designtokens.org/
- **Validator:** https://tr.designtokens.org/format/validator

### Figma Integration
- **Tokens Studio Docs:** https://docs.tokens.studio/
- **Figma Variables Guide:** https://help.figma.com/hc/en-us/articles/15339657135383

### Tooling
- **Style Dictionary:** https://amzn.github.io/style-dictionary/
- **JSON Validator:** https://jsonlint.com/

### Typography
- **Urbanist Font:** https://fonts.google.com/specimen/Urbanist
- **Google Fonts:** https://fonts.google.com/

---

## ⚡ Quick Links

| I need... | Go to... |
|-----------|----------|
| Color hex codes | `QUICK-REFERENCE.md` |
| Figma setup | `FIGMA-SETUP-GUIDE.md` |
| Logo component code | `QUICK-REFERENCE.md` → Logo section |
| Add new token | `README-DESIGN-TOKENS.md` → Updating Tokens |
| Understand workflow | `DESIGN-SYSTEM-SYNC.md` |
| Daily reference | `QUICK-REFERENCE.md` |
| Component examples | Design System page (run app) |
| Token source | `design-tokens.json` |

---

## 📊 Metrics

### Design System Stats

- **Total Tokens:** 90+
- **Color Tokens:** 34
- **Typography Tokens:** 20+
- **Spacing Tokens:** 13
- **Component Variants:** 30+
- **Logo Variations:** 7
- **Documentation Pages:** 6

### Setup Time

- **Designer onboarding:** ~15 min
- **Developer onboarding:** ~20 min
- **Figma sync setup:** ~5 min
- **First component build:** ~10 min

---

## 🎯 Success Criteria

You're successfully using the design system when:

✅ Designers use Figma Variables for all colors  
✅ Developers use tokens (not hardcoded values)  
✅ New components match existing style  
✅ Design and code stay in sync  
✅ Token changes propagate to both platforms  
✅ Team refers to documentation regularly  

---

## 🤝 Contributing

### Requesting New Tokens

1. Create GitHub issue
2. Describe use case
3. Suggest token name and value
4. Developer adds to `design-tokens.json`
5. Syncs to Figma
6. Available in both platforms

### Proposing Components

1. Share design mockup
2. Discuss with team
3. Add to Design System page
4. Document usage
5. Share with team

---

## 📞 Getting Help

### For Quick Questions
- Check `QUICK-REFERENCE.md` first
- Search this index for relevant doc

### For Figma Issues
- Read `FIGMA-SETUP-GUIDE.md`
- Check Tokens Studio docs

### For Token Questions
- Read `README-DESIGN-TOKENS.md`
- Review `design-tokens.json` structure

### For Workflow Questions
- Read `DESIGN-SYSTEM-SYNC.md`
- Ask in team channel

---

## 🎉 You're Ready!

Pick your role above, follow the "Must Read" docs, and you'll be productive with the design system in under 20 minutes.

**Bookmark this page** as your central hub for all design system documentation.

---

**Veridex Design System v1.0**  
**Last Updated:** March 2026  
**Maintained By:** Platform Team
