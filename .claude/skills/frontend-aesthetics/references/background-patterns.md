# Background Patterns & Atmospheres

Avoid solid colors. Create depth and atmosphere instead.

## CSS-Only Patterns

### 1. Gradient Meshes

```css
/* Multi-point radial mesh */
.mesh-gradient {
  background:
    radial-gradient(at 27% 37%, hsla(215, 98%, 61%, 0.12) 0px, transparent 50%),
    radial-gradient(at 97% 21%, hsla(125, 98%, 72%, 0.12) 0px, transparent 50%),
    radial-gradient(at 52% 99%, hsla(354, 98%, 61%, 0.12) 0px, transparent 50%),
    radial-gradient(at 10% 29%, hsla(256, 96%, 67%, 0.12) 0px, transparent 50%),
    radial-gradient(at 74% 75%, hsla(47, 98%, 61%, 0.12) 0px, transparent 50%);
  background-color: #0A0A0A;
}

/* Organic blob gradient */
.blob-gradient {
  background:
    radial-gradient(
      ellipse 80% 50% at 50% 40%,
      rgba(255, 107, 107, 0.15),
      transparent
    ),
    radial-gradient(
      ellipse 60% 70% at 30% 70%,
      rgba(0, 217, 255, 0.15),
      transparent
    );
  background-color: #1A1A1A;
}

/* Spotlight effect (combine with JS for cursor tracking) */
.spotlight {
  background: radial-gradient(
    600px circle at var(--mouse-x, 50%) var(--mouse-y, 50%),
    rgba(255, 255, 255, 0.06),
    transparent 40%
  );
  background-color: #000000;
}
```

**JavaScript for cursor tracking:**
```javascript
document.addEventListener('mousemove', (e) => {
  const x = e.clientX / window.innerWidth * 100;
  const y = e.clientY / window.innerHeight * 100;
  document.documentElement.style.setProperty('--mouse-x', `${x}%`);
  document.documentElement.style.setProperty('--mouse-y', `${y}%`);
});
```

### 2. Grid Patterns

```css
/* Subtle grid */
.grid-subtle {
  background-color: #0A0A0A;
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
  background-size: 50px 50px;
}

/* Perspective grid (creates depth) */
.grid-perspective {
  background-color: #000000;
  background-image:
    linear-gradient(rgba(0, 255, 255, 0.1) 2px, transparent 2px),
    linear-gradient(90deg, rgba(0, 255, 255, 0.1) 2px, transparent 2px);
  background-size: 50px 50px;
  background-position: center center;
  transform: perspective(500px) rotateX(60deg);
  transform-origin: center center;
}

/* Blueprint grid */
.grid-blueprint {
  background-color: #0C4A6E;
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.1) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.1) 1px, transparent 1px),
    linear-gradient(rgba(255, 255, 255, 0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
  background-size: 100px 100px, 100px 100px, 20px 20px, 20px 20px;
}

/* Isometric grid */
.grid-isometric {
  background-color: #1A1A1A;
  background-image:
    linear-gradient(30deg, rgba(255, 255, 255, 0.05) 12%, transparent 12.5%, transparent 87%, rgba(255, 255, 255, 0.05) 87.5%),
    linear-gradient(150deg, rgba(255, 255, 255, 0.05) 12%, transparent 12.5%, transparent 87%, rgba(255, 255, 255, 0.05) 87.5%),
    linear-gradient(30deg, rgba(255, 255, 255, 0.05) 12%, transparent 12.5%, transparent 87%, rgba(255, 255, 255, 0.05) 87.5%),
    linear-gradient(150deg, rgba(255, 255, 255, 0.05) 12%, transparent 12.5%, transparent 87%, rgba(255, 255, 255, 0.05) 87.5%);
  background-size: 80px 140px;
  background-position: 0 0, 0 0, 40px 70px, 40px 70px;
}
```

### 3. Dot Patterns

```css
/* Simple dots */
.dots-simple {
  background-color: #0A0A0A;
  background-image: radial-gradient(
    circle,
    rgba(255, 255, 255, 0.1) 1px,
    transparent 1px
  );
  background-size: 20px 20px;
}

/* Variable size dots */
.dots-variable {
  background-color: #1A1A1A;
  background-image:
    radial-gradient(circle, rgba(255, 255, 255, 0.15) 2px, transparent 2px),
    radial-gradient(circle, rgba(255, 255, 255, 0.08) 1px, transparent 1px);
  background-size: 40px 40px, 20px 20px;
  background-position: 0 0, 20px 20px;
}

/* Halftone pattern */
.dots-halftone {
  background-color: #000000;
  background-image:
    radial-gradient(circle, rgba(255, 0, 255, 0.3) 10%, transparent 10%),
    radial-gradient(circle, rgba(0, 255, 255, 0.3) 10%, transparent 10%);
  background-size: 30px 30px;
  background-position: 0 0, 15px 15px;
}
```

### 4. Line Patterns

```css
/* Diagonal lines */
.lines-diagonal {
  background-color: #0A0A0A;
  background-image: repeating-linear-gradient(
    45deg,
    transparent,
    transparent 10px,
    rgba(255, 255, 255, 0.03) 10px,
    rgba(255, 255, 255, 0.03) 11px
  );
}

/* Vertical lines (code editor style) */
.lines-vertical {
  background-color: #1A1A1A;
  background-image: repeating-linear-gradient(
    90deg,
    transparent,
    transparent 79px,
    rgba(255, 255, 255, 0.05) 79px,
    rgba(255, 255, 255, 0.05) 80px
  );
}

/* Crosshatch */
.lines-crosshatch {
  background-color: #0A0A0A;
  background-image:
    repeating-linear-gradient(
      45deg,
      transparent,
      transparent 10px,
      rgba(255, 255, 255, 0.03) 10px,
      rgba(255, 255, 255, 0.03) 11px
    ),
    repeating-linear-gradient(
      -45deg,
      transparent,
      transparent 10px,
      rgba(255, 255, 255, 0.03) 10px,
      rgba(255, 255, 255, 0.03) 11px
    );
}
```

### 5. Noise Textures

```css
/* CSS noise via SVG filter */
.noise-texture {
  background-color: #1A1A1A;
  position: relative;
}

.noise-texture::before {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.05;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 400 400' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' /%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' /%3E%3C/svg%3E");
  pointer-events: none;
}

/* Grain overlay */
.grain-overlay {
  background-color: #0A0A0A;
  position: relative;
}

.grain-overlay::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='3.5' numOctaves='1' /%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' opacity='0.3'/%3E%3C/svg%3E");
  opacity: 0.08;
  mix-blend-mode: overlay;
  pointer-events: none;
}
```

## Animated Backgrounds

### 1. Gradient Shifts

```css
/* Slow color shift */
@keyframes gradientShift {
  0%, 100% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
}

.animated-gradient {
  background: linear-gradient(
    -45deg,
    #1A1A1A,
    #2D1B4E,
    #1A1A1A,
    #1B3A4E
  );
  background-size: 400% 400%;
  animation: gradientShift 15s ease infinite;
}

/* Aurora effect */
@keyframes aurora {
  0%, 100% {
    opacity: 0.3;
    transform: translateY(0) scale(1);
  }
  50% {
    opacity: 0.6;
    transform: translateY(-20px) scale(1.1);
  }
}

.aurora-effect {
  background-color: #0A0A0A;
  position: relative;
  overflow: hidden;
}

.aurora-effect::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(
    ellipse at center,
    rgba(88, 166, 255, 0.3) 0%,
    rgba(139, 92, 246, 0.2) 50%,
    transparent 70%
  );
  animation: aurora 10s ease-in-out infinite;
}
```

### 2. Floating Particles

```css
@keyframes float {
  0%, 100% {
    transform: translateY(0px) translateX(0px);
  }
  25% {
    transform: translateY(-20px) translateX(10px);
  }
  50% {
    transform: translateY(-40px) translateX(-5px);
  }
  75% {
    transform: translateY(-20px) translateX(-15px);
  }
}

.particle {
  position: absolute;
  width: 4px;
  height: 4px;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  animation: float 15s ease-in-out infinite;
}

.particle:nth-child(2) { animation-delay: 2s; }
.particle:nth-child(3) { animation-delay: 4s; }
.particle:nth-child(4) { animation-delay: 6s; }
```

### 3. Scanlines

```css
@keyframes scanline {
  0% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(100vh);
  }
}

.scanlines {
  background-color: #0A0A0A;
  position: relative;
  overflow: hidden;
}

.scanlines::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(
    to bottom,
    transparent,
    rgba(0, 255, 255, 0.5),
    transparent
  );
  animation: scanline 8s linear infinite;
}

.scanlines::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image: repeating-linear-gradient(
    0deg,
    rgba(0, 0, 0, 0.1),
    rgba(0, 0, 0, 0.1) 1px,
    transparent 1px,
    transparent 2px
  );
  pointer-events: none;
}
```

### 4. Matrix Rain

```css
@keyframes matrixRain {
  0% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(100vh);
  }
}

.matrix-bg {
  background-color: #000000;
  position: relative;
  overflow: hidden;
}

.matrix-bg .column {
  position: absolute;
  top: -100%;
  font-family: 'Courier New', monospace;
  font-size: 14px;
  color: #00FF41;
  text-shadow: 0 0 8px #00FF41;
  animation: matrixRain 10s linear infinite;
  opacity: 0.7;
}

/* Use JS to generate multiple columns */
```

## Context-Specific Patterns

### Developer Tools

```css
/* Terminal-like */
.terminal-bg {
  background-color: #0D1117;
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.02) 1px, transparent 1px);
  background-size: 100% 20px;
  font-family: 'JetBrains Mono', monospace;
}

/* Code editor */
.code-editor-bg {
  background-color: #1E1E1E;
  background-image:
    linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
  background-size: 80px 100%;
  background-position: 40px 0;
}
```

### Creative/Art

```css
/* Paint strokes */
.paint-strokes {
  background-color: #FAF7FC;
  background-image:
    linear-gradient(110deg, #e0b3ff 0%, #e0b3ff 25%, transparent 25%),
    linear-gradient(110deg, transparent 75%, #ffd1dc 75%);
  background-size: 100% 200%;
  background-position: 0% 0%;
}

/* Canvas texture */
.canvas-texture {
  background-color: #FFF8F0;
  background-image:
    repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.02) 2px, rgba(0,0,0,0.02) 4px),
    repeating-linear-gradient(90deg, transparent, transparent 2px, rgba(0,0,0,0.02) 2px, rgba(0,0,0,0.02) 4px);
}
```

### Wellness/Meditation

```css
/* Soft glow */
.soft-glow {
  background: radial-gradient(
    ellipse at center,
    rgba(255, 193, 122, 0.1) 0%,
    rgba(156, 89, 182, 0.1) 50%,
    rgba(45, 27, 62, 1) 100%
  );
}

/* Organic waves */
.organic-waves {
  background:
    linear-gradient(180deg, transparent 50%, rgba(255, 193, 122, 0.1) 100%),
    radial-gradient(ellipse at top, rgba(156, 89, 182, 0.2), transparent 70%);
  background-color: #2D1B3E;
}
```

## Layering Techniques

### Combine Multiple Effects

```css
.rich-background {
  /* Layer 1: Base color */
  background-color: #0A0A0A;

  /* Layer 2: Grid */
  background-image:
    linear-gradient(rgba(255, 255, 255, 0.02) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.02) 1px, transparent 1px),
    /* Layer 3: Radial glow */
    radial-gradient(
      ellipse at 20% 50%,
      rgba(88, 166, 255, 0.1) 0%,
      transparent 50%
    );

  background-size: 40px 40px, 40px 40px, 100% 100%;
  background-position: 0 0, 0 0, 0 0;
  position: relative;
}

/* Layer 4: Noise (via pseudo-element) */
.rich-background::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,...");
  opacity: 0.05;
  pointer-events: none;
}
```

## Performance Tips

1. **Use CSS over Images** - Faster load times, scalable
2. **Limit Animations** - Only animate what's necessary
3. **Use `will-change`** - For animated elements
4. **Reduce Blur Radius** - Large blurs are expensive
5. **Consolidate Layers** - Don't stack too many gradients

```css
/* Performant */
.optimized {
  background: linear-gradient(/* ... */);
  will-change: background-position; /* Only if animating */
}

/* Avoid */
.heavy {
  background:
    radial-gradient(/* ... */),
    radial-gradient(/* ... */),
    radial-gradient(/* ... */),
    radial-gradient(/* ... */),
    radial-gradient(/* ... */),
    linear-gradient(/* ... */); /* Too many layers */
  filter: blur(40px); /* Expensive blur */
}
```

## Quick Reference

| Context | Pattern | Vibe |
|---------|---------|------|
| Developer Tools | Grid + Scanlines | Technical, precise |
| Creative Agency | Paint Strokes + Mesh | Artistic, bold |
| Finance App | Subtle Grid + Glow | Professional, trustworthy |
| Wellness App | Organic Waves + Soft Glow | Calming, warm |
| Gaming | Matrix Rain + Neon | Energetic, cyber |
| E-commerce | Clean Gradient Mesh | Modern, premium |
| Portfolio | Spotlight + Noise | Dramatic, focused |
| Documentation | Code Editor + Lines | Clear, organized |

Remember: The background should create **atmosphere without competing** with content.
