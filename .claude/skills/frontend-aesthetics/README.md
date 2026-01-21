# Frontend Aesthetics Skill

**A Claude Code skill for creating distinctive, memorable frontend designs that avoid generic "AI slop" aesthetics.**

## Purpose

This skill guides you to create bold, contextual, and unexpected design choices that surprise and delight users. It actively combats convergence toward generic patterns by encouraging creative typography, committed color palettes, orchestrated animations, and atmospheric backgrounds.

## Structure

```
frontend-aesthetics/
├── SKILL.md                          # Main skill instructions
├── README.md                         # This file
├── references/
│   ├── font-pairings.md             # 10+ distinctive font combinations
│   ├── color-palettes.md            # 10+ theme examples with code
│   └── background-patterns.md       # CSS patterns and atmospheres
└── assets/
    └── design-system-template.css   # Complete design system starter
```

## When This Skill Activates

Claude will use this skill when you:
- Design UI components or pages
- Choose typography and fonts
- Create color schemes and themes
- Implement animations and motion design
- Design backgrounds and visual atmosphere
- Build design systems or style guides

## Core Principles

### 1. Typography: Choose Character Over Ubiquity

**Avoid:**
- Inter, Roboto, Arial, System fonts, Space Grotesk

**Explore:**
- Display: Cabinet Grotesk, Clash Display, Obviously
- Serif: Tiempos, Crimson Pro, Spectral, Fraunces
- Mono: JetBrains Mono, Departure Mono
- Sans: Untitled Sans, Switzer, ABC Favorit

See `references/font-pairings.md` for 10+ proven combinations.

### 2. Color: Dominant + Sharp Accent

**Avoid:**
- Purple gradients on white (#8B5CF6 → #EC4899)
- Evenly-distributed rainbow palettes
- Timid, low-contrast schemes

**Do:**
- Commit to a dominant color (60%)
- Add sharp accent colors (10%)
- Fill with thoughtful neutrals (30%)
- Draw inspiration from IDE themes, cultural aesthetics

See `references/color-palettes.md` for 10+ distinctive themes.

### 3. Motion: Orchestrate High-Impact Moments

**Priority:**
1. Page load choreography (staggered reveals)
2. State transitions (loading → content)
3. User interactions (hovers, clicks)
4. Ambient motion (subtle effects)

**Prefer CSS-only** for HTML, use Framer Motion for React.

### 4. Backgrounds: Create Atmosphere

**Avoid:**
- Solid colors (`background: #FFFFFF`)

**Instead:**
- Layered CSS gradients
- Geometric patterns (grids, dots)
- Noise textures
- Contextual effects (spotlight, animated meshes)

See `references/background-patterns.md` for dozens of patterns.

## Usage Examples

### Example 1: Developer Tool Aesthetic

```css
:root {
  --font-display: 'JetBrains Mono', monospace;
  --font-body: 'Spectral', serif;
  --bg-base: #0D1117;
  --accent: #58A6FF;
  --accent-sharp: #FF7B72;
}

.hero {
  background:
    radial-gradient(circle at 20% 50%, rgba(88, 166, 255, 0.1) 0%, transparent 50%),
    linear-gradient(rgba(255, 255, 255, 0.02) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.02) 1px, transparent 1px),
    #0D1117;
  background-size: 100% 100%, 40px 40px, 40px 40px;
}
```

### Example 2: Editorial Aesthetic

```css
:root {
  --font-display: 'Tiempos Headline', serif;
  --font-body: 'Untitled Sans', sans-serif;
  --bg-base: #FAF7FC;
  --text-primary: #2D1B3D;
  --accent: #9D4EDD;
}

/* Staggered page load */
.article-header > * {
  animation: fadeInUp 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
  animation-fill-mode: backwards;
}

.article-header > *:nth-child(1) { animation-delay: 0.1s; }
.article-header > *:nth-child(2) { animation-delay: 0.3s; }
.article-header > *:nth-child(3) { animation-delay: 0.5s; }
```

### Example 3: Quick Start with Template

```bash
# Copy the design system template
cp .claude/skills/frontend-aesthetics/assets/design-system-template.css src/styles/design-system.css

# Customize the variables
# - Replace font families with distinctive choices
# - Replace colors with your committed palette
# - Add context-specific patterns from references/
```

## Quick Checklist

Before finalizing any design, verify:

**Typography:**
- [ ] Font is distinctive (not Inter/Roboto/Arial)
- [ ] Haven't used this font recently
- [ ] Type scale is consistent

**Color:**
- [ ] Clear dominant color + sharp accent
- [ ] Not purple gradient on white
- [ ] CSS variables defined

**Motion:**
- [ ] Page load has orchestrated reveal
- [ ] Custom easings (not just `ease-in-out`)
- [ ] Stagger delays create rhythm

**Backgrounds:**
- [ ] Not solid colors
- [ ] Creates depth/atmosphere
- [ ] Matches overall aesthetic

**Overall:**
- [ ] Design feels unique to context
- [ ] Choices are bold and committed
- [ ] Layout isn't predictable

## Resources

### Reference Files

- **`font-pairings.md`**: 10+ proven font combinations with context
- **`color-palettes.md`**: 10+ distinctive theme examples with full code
- **`background-patterns.md`**: CSS-only patterns and animations

### Assets

- **`design-system-template.css`**: Production-ready design system starter with:
  - Typography scale and font loading
  - Color system with CSS variables
  - Spacing scale (4px base)
  - Animation timing and easings
  - Responsive breakpoints
  - Example components

## Philosophy

**Your goal is to create designs that feel:**
- ✅ Intentional and context-aware
- ✅ Distinctive and memorable
- ✅ Surprising yet appropriate
- ✅ Crafted, not templated

**Ask yourself:**
- "Have I seen this exact design before?"
- "Does this feel generic or specific?"
- "Am I making bold choices or safe ones?"
- "Will users remember this experience?"

If the answer suggests generic, iterate until it's distinctive.

## Tips for Claude Code

When using this skill:

1. **Always vary your choices** - Don't use the same fonts/colors across projects
2. **Be contextual** - A finance app should look nothing like a meditation app
3. **Commit to aesthetics** - Half-measures create generic results
4. **Think outside the box** - The first idea is often too safe
5. **Use the references** - They contain dozens of proven patterns

## Examples of What NOT to Do

```css
/* ❌ Generic AI Slop */
--font: 'Inter', sans-serif;
background: linear-gradient(135deg, #8B5CF6 0%, #EC4899 100%);
border-radius: 12px;
box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
```

## Examples of What TO Do

```css
/* ✅ Distinctive and Contextual */
--font-display: 'Cabinet Grotesk', sans-serif;
--font-body: 'Spectral', serif;
background:
  radial-gradient(at 20% 50%, rgba(255, 107, 107, 0.15), transparent 50%),
  radial-gradient(at 80% 80%, rgba(0, 217, 255, 0.15), transparent 50%),
  #0F1419;
border-left: 3px solid var(--accent);
box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
```

---

**Remember:** Be bold. Be unexpected. Be contextual. Avoid the generic, embrace the distinctive.
