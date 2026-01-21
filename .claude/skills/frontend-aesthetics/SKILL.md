---
name: frontend-aesthetics
description: Design futuristic, data-driven UI for signal discovery SaaS. Focus on intelligent layouts, subtle sophistication, dynamic React components, and original data visualizations. Avoid generic patterns and bright accent colors.
---

# Frontend Aesthetics - SignalScan

## Purpose

Create a modern, slick, futuristic tech aesthetic for a signal discovery platform. Focus on intelligent data visualization, asymmetric layouts, and subtle sophistication that conveys technological prowess without garish colors.

## Context: Signal Discovery SaaS

**What we're building:** A platform that helps entrepreneurs discover signals on social platforms, validate ideas, and find potential customers.

**Design Goals:**
- **HIGH PRIORITY:** Interactive segment comparison (Venn diagrams, overlap analysis, demographic contrast)
- Convey data intelligence and analytical power
- Push frontend limits with dynamic, AI-assisted exploration
- Smart layouts that highlight insights
- Professional yet innovative

**Avoid:**
- Generic SaaS templates (purple gradients, centered hero sections)
- Bright, high-contrast accent colors (purple, orange)
- Static charts and boring data tables

## 1. Typography: Tech-Forward & Readable

```css
/* Recommended: Data Intelligence */
--font-display: 'JetBrains Mono', monospace;  /* Headings, metrics */
--font-body: 'Geist', sans-serif;             /* Body, UI text */
--font-data: 'JetBrains Mono', monospace;     /* Tables, numbers */

/* Alternative: Modern Precision */
--font-display: 'ABC Favorit', sans-serif;
--font-body: 'ABC Favorit', sans-serif;
--font-data: 'IBM Plex Mono', monospace;
```

**Key principles:** Monospace for metrics (precision), geometric sans-serifs (tech feel), tabular figures for data alignment.

## 2. Color: Subtle Sophistication

**Avoid:** Purple (#8B5CF6), Orange (#FF7F00), bright high-contrast accent colors

**Signal Discovery Palette:**

```css
:root {
  /* Base - Deep space dark */
  --bg-base: #0A0E14;
  --bg-elevated: #12171F;
  --bg-overlay: #1A2332;
  --bg-inset: #080B10;

  /* Text - Cool grays */
  --text-primary: #E6EDF3;
  --text-secondary: #8B99AC;
  --text-tertiary: #586978;

  /* Data accent - Subtle cyan/teal (NOT bright) */
  --data-primary: #5FBDCE;      /* Soft cyan */
  --data-secondary: #4A9BA8;    /* Muted teal */
  --data-highlight: #7DD3E0;    /* Light cyan for highlights */

  /* Semantic - Muted, professional */
  --success: #52BD95;    /* Muted green */
  --warning: #D4A574;    /* Soft amber */
  --error: #D67676;      /* Muted red */
  --info: #6B9DD6;       /* Soft blue */

  /* Borders - Subtle separation */
  --border: #1F2936;
  --border-subtle: #161B24;
  --border-focus: #5FBDCE;

  /* Data visualization spectrum (avoid purple/orange) */
  --viz-1: #5FBDCE;  /* Cyan */
  --viz-2: #6B9DD6;  /* Blue */
  --viz-3: #52BD95;  /* Green */
  --viz-4: #D4A574;  /* Amber */
  --viz-5: #8B99AC;  /* Gray */
}
```

**Color Usage:**
- Dark backgrounds create depth for data to pop
- Cyan/teal accents feel analytical, not playful
- Muted palette = professional, not toy-like
- Use color strategically for data categories, not decoration

## 3. Motion: Dynamic Data Transitions

**Focus on data state transitions, not decorative animations.**

**React + Framer Motion Patterns:**

```jsx
import { motion, AnimatePresence } from "framer-motion";

// Data loading → reveal
const DataCard = ({ data, isLoading }) => (
  <AnimatePresence mode="wait">
    {isLoading ? (
      <motion.div
        key="skeleton"
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        exit={{ opacity: 0 }}
      >
        <Skeleton />
      </motion.div>
    ) : (
      <motion.div
        key="data"
        initial={{ opacity: 0, y: 10 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.3, ease: [0.4, 0, 0.2, 1] }}
      >
        {data}
      </motion.div>
    )}
  </AnimatePresence>
);

// Staggered list reveal (signals feed)
const containerVariants = {
  hidden: { opacity: 0 },
  visible: {
    opacity: 1,
    transition: { staggerChildren: 0.05 }
  }
};

const itemVariants = {
  hidden: { opacity: 0, x: -20 },
  visible: {
    opacity: 1,
    x: 0,
    transition: { duration: 0.3 }
  }
};

// Number count-up animation for metrics
const AnimatedMetric = ({ value }) => {
  const [count, setCount] = useState(0);
  useEffect(() => {
    const controls = animate(0, value, {
      duration: 1,
      onUpdate: v => setCount(Math.floor(v))
    });
    return controls.stop;
  }, [value]);
  return <span>{count.toLocaleString()}</span>;
};
```

## 4. Backgrounds: Data-Driven Atmosphere

**Tech patterns that suggest connectivity and intelligence:**

```css
/* Hero - Subtle grid with glow */
.hero-background {
  background:
    /* Soft cyan glow */
    radial-gradient(
      ellipse 800px 600px at 30% 40%,
      rgba(95, 189, 206, 0.08),
      transparent
    ),
    /* Fine grid */
    linear-gradient(rgba(230, 237, 243, 0.02) 1px, transparent 1px),
    linear-gradient(90deg, rgba(230, 237, 243, 0.02) 1px, transparent 1px),
    /* Base */
    #0A0E14;
  background-size: 100% 100%, 40px 40px, 40px 40px, 100% 100%;
}

/* Dashboard - Noise texture for depth */
.dashboard-bg {
  background-color: #0A0E14;
  position: relative;
}

.dashboard-bg::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence baseFrequency='0.9' numOctaves='3'/%3E%3C/filter%3E%3Crect width='200' height='200' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
  pointer-events: none;
}

/* Data cards - Elevated surfaces */
.data-card {
  background: linear-gradient(
    135deg,
    rgba(18, 23, 31, 0.8),
    rgba(26, 35, 50, 0.6)
  );
  border: 1px solid var(--border);
  backdrop-filter: blur(8px);
}

/* Spotlight effect for interactive areas */
.interactive-section {
  background: radial-gradient(
    600px circle at var(--mouse-x, 50%) var(--mouse-y, 50%),
    rgba(95, 189, 206, 0.04),
    transparent 50%
  );
}
```

## 5. Smart Layouts for Data

**Asymmetric, intelligence-focused layouts:**

**Dashboard Grid - Bento Box Style:**
```jsx
<div className="dashboard-grid">
  {/* Large featured metric - spans 2 columns */}
  <Card className="col-span-2 row-span-2">
    <MetricDisplay value={12500} label="Signals Found" />
  </Card>

  {/* Small quick stats */}
  <Card><QuickStat /></Card>
  <Card><QuickStat /></Card>

  {/* Wide chart */}
  <Card className="col-span-3">
    <TrendChart />
  </Card>

  {/* Tall feed */}
  <Card className="row-span-3">
    <SignalFeed />
  </Card>
</div>

<style>
.dashboard-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  grid-auto-rows: 180px;
}
</style>
```

**Signal Card - Asymmetric Info Density:**
```jsx
// Not centered - left-aligned with right-side metadata
<div className="signal-card">
  <div className="signal-content">
    <h3>{title}</h3>
    <p>{excerpt}</p>
    <div className="signal-meta">
      <Badge>{subreddit}</Badge>
      <Stat icon={<ArrowUp />} value={score} />
    </div>
  </div>

  <div className="signal-viz">
    <MiniSparkline data={trend} />
  </div>
</div>

<style>
.signal-card {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 2rem;
  align-items: start; /* Not centered */
}
</style>
```

## 6. Data Visualization Components

**Original, dynamic visualizations (not boring tables):**

```jsx
// Signal strength indicator - custom component
const SignalStrength = ({ value }) => (
  <motion.div className="signal-bars">
    {[0, 1, 2, 3, 4].map(i => (
      <motion.div
        key={i}
        className="bar"
        initial={{ scaleY: 0 }}
        animate={{ scaleY: value > i ? 1 : 0.3 }}
        transition={{ delay: i * 0.05 }}
        style={{
          height: `${(i + 1) * 20}%`,
          opacity: value > i ? 1 : 0.3
        }}
      />
    ))}
  </motion.div>
);

// Trend sparkline with gradient fill
const TrendSparkline = ({ data }) => (
  <svg viewBox="0 0 100 30" className="sparkline">
    <defs>
      <linearGradient id="gradient" x1="0" x2="0" y1="0" y2="1">
        <stop offset="0%" stopColor="var(--data-primary)" stopOpacity="0.3" />
        <stop offset="100%" stopColor="var(--data-primary)" stopOpacity="0" />
      </linearGradient>
    </defs>
    <motion.path
      d={generatePath(data)}
      fill="url(#gradient)"
      stroke="var(--data-primary)"
      strokeWidth="2"
      initial={{ pathLength: 0 }}
      animate={{ pathLength: 1 }}
      transition={{ duration: 1, ease: "easeOut" }}
    />
  </svg>
);

// Sentiment gauge - radial progress with animation
const SentimentGauge = ({ positive }) => (
  <svg viewBox="0 0 100 100">
    <motion.circle
      cx="50" cy="50" r="40" stroke="var(--success)" strokeWidth="8"
      fill="none" strokeDasharray={`${positive * 2.51} 251`}
      initial={{ strokeDashoffset: 251 }}
      animate={{ strokeDashoffset: 0 }}
    />
  </svg>
);

// Network graph with D3 + Framer Motion for positioning/transitions
```

## 7. Interactive Segment Comparison (HIGH PRIORITY)

**Dynamic components for exploring audience overlaps and contrasts:**

```jsx
import { motion, AnimatePresence } from "framer-motion";
import { useState } from "react";

// Interactive Venn Diagram - shows segment overlap
const InteractiveVenn = ({ segmentA, segmentB, overlap }) => (
  <svg viewBox="0 0 400 300" className="venn-diagram">
    <motion.circle cx="130" cy="150" r="80" fill="var(--viz-1)" fillOpacity="0.3"
      stroke="var(--viz-1)" strokeWidth="2" whileHover={{ scale: 1.05, fillOpacity: 0.5 }} />
    <motion.circle cx="270" cy="150" r="80" fill="var(--viz-2)" fillOpacity="0.3"
      stroke="var(--viz-2)" strokeWidth="2" whileHover={{ scale: 1.05, fillOpacity: 0.5 }} />
    <motion.path d="M 200 150 A 80 80 0 0 0 200 150 Z" fill="var(--data-primary)"
      fillOpacity="0.6" whileHover={{ fillOpacity: 0.8 }} />
    <text x="100" y="150">{segmentA.name}<tspan x="100" y="170">{segmentA.count}</tspan></text>
    <text x="240" y="150">{segmentB.name}<tspan x="240" y="170">{segmentB.count}</tspan></text>
    <text x="200" y="155" fontWeight="bold">{overlap}% overlap</text>
  </svg>
);

// Segment Comparison Matrix - side-by-side analysis
const SegmentMatrix = ({ segments }) => (
  <div className="comparison-matrix">
    {segments.map((segment, i) => (
      <motion.div
        key={segment.id}
        className="segment-column"
        initial={{ opacity: 0, x: -20 }}
        animate={{ opacity: 1, x: 0 }}
        transition={{ delay: i * 0.1 }}
      >
        <h3>{segment.name}</h3>
        <div className="metrics">
          <Metric label="Size" value={segment.size} />
          <Metric label="Engagement" value={segment.engagement} />
          <Metric label="Pain Points" value={segment.painPoints.length} />
        </div>
        <div className="pain-points">
          {segment.painPoints.map(point => (
            <motion.div
              key={point}
              className="pain-point-tag"
              whileHover={{ scale: 1.05, backgroundColor: 'var(--data-highlight)' }}
            >
              {point}
            </motion.div>
          ))}
        </div>
      </motion.div>
    ))}
  </div>
);

// Scatter Plot - cluster viz with interactive filters
const SegmentScatterPlot = ({ data, onFilterChange }) => (
  <div className="scatter-plot-container">
    <svg viewBox="0 0 600 400">
      <AnimatePresence>
        {data.map(point => (
          <motion.circle key={point.id} cx={point.x} cy={point.y} r={point.size}
            fill={point.color} initial={{ scale: 0 }} animate={{ scale: 1, opacity: 0.7 }}
            whileHover={{ scale: 1.5 }} layoutId={point.id} />
        ))}
      </AnimatePresence>
      <line x1="50" y1="350" x2="550" y2="350" stroke="var(--border)" />
      <line x1="50" y1="50" x2="50" y2="350" stroke="var(--border)" />
      <text x="300" y="385">Tech Affinity →</text>
      <text x="15" y="200" transform="rotate(-90 15 200)">Price Sensitivity →</text>
    </svg>
    <div className="filter-panel">
      <DraggableSlider label="Age" onChange={onFilterChange} />
      <DraggableSlider label="Income" onChange={onFilterChange} />
      <ToggleGroup options={['AI', 'Spirituality', 'Privacy']} />
    </div>
  </div>
);

// AI Insight Panel - generated segment analysis
const AIInsightPanel = ({ segmentA, segmentB }) => {
  const [insights, setInsights] = useState([]);
  const [isGenerating, setIsGenerating] = useState(false);

  return (
    <motion.div className="ai-insight-panel">
      <button onClick={() => generateInsights(segmentA, segmentB, setInsights, setIsGenerating)}>
        {isGenerating ? 'Analyzing...' : 'Generate Insights'}
      </button>
      <AnimatePresence mode="wait">
        {isGenerating ? (
          <motion.div><div className="loading-scanner" /><span>Analyzing...</span></motion.div>
        ) : (
          <motion.div>
            {insights.map((insight, i) => (
              <motion.div key={i} initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }}
                transition={{ delay: i * 0.1 }}>
                <div>{insight.type}</div>
                <p>{insight.text}</p>
                <div>Confidence: {insight.confidence}%</div>
              </motion.div>
            ))}
          </motion.div>
        )}
      </AnimatePresence>
    </motion.div>
  );
};
```

**Example - Local AI Companion App (witchcraft women vs tech men):**
```jsx
<SegmentComparisonView>
  <InteractiveVenn
    segmentA={{ name: "Witchcraft Women", count: 12500, interests: ["tarot", "meditation"] }}
    segmentB={{ name: "Local AI Tech Men", count: 8900, interests: ["privacy", "self-hosting"] }}
    overlap={23} // 23% overlap = target market
  />
  <SegmentMatrix segments={[segmentA, segmentB]} />
  <AIInsightPanel insights={["Privacy shared (67%)", "UI preferences differ", "$12/mo sweet spot"]} />
</SegmentComparisonView>
```

## 8. Pushing Frontend Limits

**Experimental, boundary-pushing interactions:**

- **Fluid morphing between views** - use Framer Motion's `layoutId` for seamless transitions
- **3D data visualizations** - React Three Fiber for rotating segment clouds
- **Gesture-based filtering** - swipe to compare, pinch to filter
- **Real-time collaborative exploration** - multiple users exploring signals simultaneously
- **Voice-controlled segment queries** - "Show me overlap between crypto enthusiasts and minimalists"
- **Generative UI** - AI suggests new comparison dimensions based on patterns

## Quality Checklist

**Typography:** Monospace for metrics (JetBrains Mono/IBM Plex), geometric sans-serif for UI (Geist/ABC Favorit). NOT Inter/Roboto/Arial.

**Color:** Dark theme (#0A0E14), subtle cyan/teal (#5FBDCE). NO purple/orange. Muted semantics.

**Motion:** Data state transitions, staggered reveals, count-up animations, subtle hovers (2px), Framer Motion.

**Layout:** Asymmetric bento grids, left-aligned, variable card sizes, smart data density.

**Segment Comparison (PRIORITY):** Interactive Venn diagrams, comparison matrices, scatter plots with filters, AI-generated insights.

**Data Viz:** Custom sparklines, animated charts, NOT default library styles. Original designs (signal bars, gauges).

**Atmosphere:** Grid/noise textures, soft glows, backdrop blur, tech-forward (analytical, not playful).

**Final:** Futuristic data intelligence platform? Sophisticated without garish? Layouts smart, not templated?
