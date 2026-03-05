# Quick Setup: Veridex Tokens → Figma

**Goal:** Import the Veridex design system into Figma so designers can use the same colors, typography, and spacing as the web app.

---

## 🎯 Fastest Method: Tokens Studio Plugin

### Step 1: Install Tokens Studio (2 minutes)

1. Open your Figma file
2. Click **Plugins** → **Browse plugins in Community**
3. Search for **"Tokens Studio for Figma"**
4. Click **Install** (it's free)

---

### Step 2: Import design-tokens.json (3 minutes)

**Method A: Manual Import (Quickest)**

1. Open Tokens Studio plugin in Figma
2. Click **Settings** (gear icon)
3. Click **Add new** → **Empty**
4. Go to your codebase → Open `/design-tokens.json`
5. **Copy the entire file contents**
6. Back in Tokens Studio → Click **Import** (top right)
7. **Paste** the JSON → Click **Import**
8. ✅ Done! All tokens are now in Figma

**Method B: GitHub Sync (Best for teams)**

1. Open Tokens Studio → **Settings**
2. Click **Add new** → **GitHub**
3. Authenticate with GitHub
4. Select your repository
5. Set file path: `/design-tokens.json`
6. Branch: `main` (or your default branch)
7. Click **Save**
8. Tokens auto-sync whenever you push to GitHub

---

### Step 3: Apply Tokens as Figma Variables (2 minutes)

1. In Tokens Studio panel → Click **Create Variables**
2. Select all token sets → Click **Create**
3. Figma will create native Variables from your tokens
4. These appear in Figma's **Variables panel** (Shift + Cmd/Ctrl + K)

---

## 🎨 Using Tokens in Your Designs

### Colors

**Before:**
- Select layer → Fill → Pick color manually

**After:**
- Select layer → Fill → Click variable icon → Choose `color/brand/green`

### Typography

**Before:**
- Type layer → Manually set to 16px, weight 500

**After:**
- Type layer → Font size → Variable → `typography/font-size/base`
- Weight → Variable → `typography/font-weight/medium`

### Spacing

**Before:**
- Auto Layout → Gap → Type "16px"

**After:**
- Auto Layout → Gap → Variable → `spacing/4`

---

## 📋 Token Categories Available

Once imported, you'll have these variable collections:

### 🎨 Colors
```
color/brand/green         → #0be149 (Spring Green)
color/brand/navy          → #08307f (Navy Blue)
color/brand/white         → #ffffff

color/grey/50 through 900 → Neutral grays

color/status/verified     → #0be149
color/status/pending      → #f59e0b
color/status/rejected     → #d4183d

color/semantic/primary    → #08307f
color/semantic/accent     → #0be149
...and more
```

### 📝 Typography
```
typography/font-family/base  → "Urbanist, sans-serif"
typography/font-size/xs      → 12px
typography/font-size/base    → 16px
typography/font-size/xl      → 20px
typography/font-weight/medium → 500
```

### 📐 Spacing
```
spacing/1   → 4px
spacing/2   → 8px
spacing/4   → 16px
spacing/6   → 24px
spacing/8   → 32px
```

### 🎭 Other
```
radius/sm through full  → Border radius values
shadow/sm through xl    → Elevation shadows
opacity/10 through 100  → Transparency levels
```

---

## ✅ Verify Setup

### Check if it worked:

1. **Open Figma Variables panel** (Shift + Cmd/Ctrl + K)
2. You should see collections:
   - `color`
   - `typography`
   - `spacing`
   - `radius`
   - `shadow`
   - `opacity`

3. **Try using a color:**
   - Draw a rectangle
   - Select Fill → Click variable icon
   - Choose `color/brand/green`
   - Rectangle turns spring green (#0be149) ✅

---

## 🔄 Keeping Tokens Updated

### When developers update design-tokens.json:

**If using GitHub Sync:**
- Open Tokens Studio → Click **Pull from GitHub**
- New tokens appear automatically

**If using Manual Import:**
- Copy new `design-tokens.json` contents
- Tokens Studio → Import → Paste → Import
- Existing tokens update, new ones added

---

## 🎯 Common Use Cases

### Creating a Button Component

1. Draw rectangle for button background
2. Fill → Variable → `color/semantic/primary` (navy)
3. Corner radius → Variable → `radius/lg` (8px)
4. Add text layer
5. Text color → Variable → `color/semantic/primary-foreground` (white)
6. Font size → Variable → `typography/font-size/sm` (14px)

### Creating a Card

1. Draw frame
2. Fill → Variable → `color/semantic/card` (white)
3. Add shadow → `shadow/md`
4. Corner radius → `radius/xl` (12px)
5. Auto Layout padding → `spacing/6` (24px)

---

## 🚨 Troubleshooting

### "Variables not appearing in Figma"
- Click **Create Variables** in Tokens Studio panel
- Ensure you're on Figma Professional plan (free trial works)

### "GitHub sync not working"
- Check your GitHub token permissions
- Verify file path is exactly `/design-tokens.json`
- Try manual import first to test

### "Tokens look wrong"
- Verify JSON is valid at https://jsonlint.com/
- Check token format matches W3C spec
- Re-import if needed

---

## 📞 Need Help?

1. **Tokens Studio Docs:** https://docs.tokens.studio/
2. **Figma Variables Guide:** https://help.figma.com/hc/en-us/articles/15339657135383
3. **Ask the dev team:** Share screenshot of error

---

## 🎉 You're Done!

Your Figma file is now connected to the same design system as the web app. 

**Next steps:**
- Build components using variables
- Share with team
- Keep tokens synced via GitHub or manual updates

**Pro tip:** Bookmark `design-tokens.json` in your repo for quick access when updating.
