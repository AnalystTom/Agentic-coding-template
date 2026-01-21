# Font Pairing Reference

## Proven Combinations

### Developer Tools & Technical Products

```css
/* Combination 1: Technical + Readable */
--font-display: 'JetBrains Mono', monospace;
--font-body: 'Spectral', serif;
```
**Use for:** IDEs, code editors, developer platforms
**Character:** Professional yet approachable, technical but readable

```css
/* Combination 2: Terminal Aesthetic */
--font-display: 'Departure Mono', monospace;
--font-body: 'Geist', sans-serif;
```
**Use for:** CLI tools, terminal apps, DevOps platforms
**Character:** Sharp, modern, command-line inspired

### Editorial & Content-Heavy Sites

```css
/* Combination 3: Classic Editorial */
--font-display: 'Tiempos Headline', serif;
--font-body: 'Untitled Sans', sans-serif;
```
**Use for:** Magazines, blogs, content platforms
**Character:** Elegant, readable, trustworthy

```css
/* Combination 4: Modern Editorial */
--font-display: 'Lyon Text', serif;
--font-body: 'Sohne', sans-serif;
```
**Use for:** Premium content, news sites, literary platforms
**Character:** Sophisticated, authoritative, refined

### Creative & Bold Applications

```css
/* Combination 5: Playful Energy */
--font-display: 'Cabinet Grotesk', sans-serif;
--font-body: 'Switzer', sans-serif;
```
**Use for:** Creative agencies, design portfolios, art platforms
**Character:** Bold, energetic, design-forward

```css
/* Combination 6: Variable Expression */
--font-display: 'Fraunces', serif; /* Use variable axes */
--font-body: 'Satoshi', sans-serif;
```
**Use for:** Interactive experiences, creative tools
**Character:** Playful, dynamic, expressive

### Minimalist & Clean Interfaces

```css
/* Combination 7: Swiss Minimalism */
--font-display: 'ABC Favorit', sans-serif;
--font-body: 'ABC Favorit', sans-serif; /* Mono-font, different weights */
```
**Use for:** SaaS products, productivity tools, dashboards
**Character:** Clean, systematic, professional

```css
/* Combination 8: Geometric Precision */
--font-display: 'Obviously', sans-serif;
--font-body: 'Switzer', sans-serif;
```
**Use for:** Architecture, design systems, technical apps
**Character:** Precise, geometric, balanced

### Wellness & Lifestyle

```css
/* Combination 9: Warm & Inviting */
--font-display: 'Crimson Pro', serif;
--font-body: 'Untitled Sans', sans-serif;
```
**Use for:** Wellness apps, meditation platforms, lifestyle brands
**Character:** Warm, thoughtful, calming

```css
/* Combination 10: Contemporary Wellness */
--font-display: 'Newsreader', serif;
--font-body: 'General Sans', sans-serif;
```
**Use for:** Health apps, fitness platforms, nutrition sites
**Character:** Modern, trustworthy, accessible

## Free Font Alternatives

If licensing is a concern, here are high-quality free alternatives:

### Google Fonts (Use Selectively)

**Display Fonts:**
- **Fraunces** (variable, playful serif)
- **Crimson Pro** (elegant serif)
- **Newsreader** (classic serif)
- **Epilogue** (clean sans)
- **Outfit** (geometric sans)

**Body Fonts:**
- **Spectral** (screen-optimized serif)
- **Source Serif 4** (readable serif)
- **Manrope** (rounded sans)
- **DM Sans** (balanced sans)

**Monospace:**
- **JetBrains Mono** (excellent for code)
- **IBM Plex Mono** (professional)
- **Fira Code** (with ligatures)

### Adobe Fonts (Included with Creative Cloud)

- **Acumin Pro** (versatile sans)
- **Forma DJR** (geometric display)
- **Kepler** (elegant serif)
- **Myriad Pro** (clean sans)
- **Minion Pro** (classic serif)

### Bunny Fonts (Privacy-focused, GDPR-compliant alternative to Google Fonts)

Access via: `https://fonts.bunny.net/css?family=font-name`

Same fonts as Google Fonts but with better privacy.

## Font Pairing Principles

### 1. Contrast is Key

Pair fonts that are different enough to create visual interest:
- **Serif + Sans-Serif** (classic)
- **Monospace + Serif** (technical + warm)
- **Display + Neutral** (bold + restrained)

### 2. Similar Proportions

Fonts should have similar:
- X-heights (how tall lowercase letters are)
- Stroke weight (thickness)
- Overall width

### 3. Shared Personality

Fonts should complement the overall aesthetic:
- Technical product → Monospace + Clean serif
- Luxury brand → Elegant serif + Refined sans
- Creative agency → Bold display + Modern sans

### 4. Hierarchy Through Weight

Use the same font family with different weights:
```css
--font-family: 'Switzer', sans-serif;

h1 { font-weight: 700; } /* Bold */
h2 { font-weight: 600; } /* Semibold */
body { font-weight: 400; } /* Regular */
caption { font-weight: 300; } /* Light */
```

## Testing Your Pairing

Use this HTML to test font combinations:

```html
<div class="font-test">
  <h1 class="display-font">The quick brown fox jumps over the lazy dog</h1>
  <p class="body-font">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
    quis nostrud exercitation ullamco laboris.
  </p>
  <code class="mono-font">const greeting = "Hello, World!";</code>
</div>
```

**Check for:**
1. Visual harmony at different sizes
2. Readability in paragraphs
3. Distinctiveness in headings
4. Overall aesthetic fit

## Loading Fonts Efficiently

### Self-Host (Best Performance)

```css
@font-face {
  font-family: 'Your Font';
  src: url('/fonts/YourFont-Regular.woff2') format('woff2');
  font-weight: 400;
  font-style: normal;
  font-display: swap; /* Prevent FOIT */
}
```

### Variable Fonts (Single File, Multiple Weights)

```css
@font-face {
  font-family: 'Fraunces';
  src: url('/fonts/Fraunces-Variable.woff2') format('woff2-variations');
  font-weight: 100 900; /* Entire range */
  font-display: swap;
}
```

### Subset Fonts (Reduce File Size)

Only include characters you need:
- Latin basic (most English sites)
- Latin extended (European languages)
- Specific weights (400, 700 instead of 100-900)

## Common Mistakes to Avoid

❌ **Pairing two decorative fonts**
```css
/* Too much personality, fights for attention */
--font-display: 'Fraunces', serif;
--font-body: 'Cabinet Grotesk', sans-serif;
```

❌ **Using too many font families**
```css
/* Inconsistent, chaotic */
--font-display: 'Font A';
--font-body: 'Font B';
--font-accent: 'Font C';
--font-mono: 'Font D';
```

❌ **Ignoring font weights**
```css
/* Using only one weight limits hierarchy */
font-family: 'Your Font';
font-weight: 400; /* Only ever using regular */
```

✅ **Do This Instead**
```css
/* Two complementary families, multiple weights */
--font-display: 'Tiempos Headline', serif;
--font-body: 'Untitled Sans', sans-serif;

h1 { font-family: var(--font-display); font-weight: 700; }
h2 { font-family: var(--font-display); font-weight: 600; }
body { font-family: var(--font-body); font-weight: 400; }
small { font-family: var(--font-body); font-weight: 300; }
```

## Quick Reference

| Context | Display Font | Body Font | Character |
|---------|--------------|-----------|-----------|
| Developer Tools | JetBrains Mono | Spectral | Technical + Warm |
| Editorial | Tiempos | Untitled Sans | Classic + Modern |
| Creative Agency | Cabinet Grotesk | Switzer | Bold + Clean |
| SaaS Product | ABC Favorit | ABC Favorit | Minimal + Pro |
| Wellness App | Crimson Pro | Untitled Sans | Warm + Clear |
| Finance App | Styrene | Sohne | Sharp + Trust |
| E-commerce | Lyon Text | General Sans | Luxury + Access |
| Documentation | IBM Plex Mono | Source Serif 4 | Code + Read |
