# MegaBrain Design System — Cline Skill

> Copy the instruction block below into Cline's **Custom Instructions** field (Settings gear → Custom Instructions).

---

## Instruction

```
When creating any HTML, CSS, or visual output, follow the MegaBrain Design System:

COLORS:
- Page background: #09090b
- Card/section background: #18181b
- Border color: #27272a
- Primary text: #fafafa
- Secondary/muted text: #a1a1aa
- Brand accent (headings, highlights): #e4530a
- Success/code: #22c55e
- Link hover: #e4530a

TYPOGRAPHY:
- Font stack: system-ui, -apple-system, 'Segoe UI', sans-serif
- Heading sizes: h1=2.5rem, h2=1.75rem, h3=1.25rem
- Heading weight: 700-800, letter-spacing: -0.02em
- Body line-height: 1.65
- Monospace: 'JetBrains Mono', 'Fira Code', monospace

COMPONENT PATTERNS:
- Cards: background #18181b, border 1px solid #27272a, border-radius 16px, padding 24px
- Badges: border-radius 999px, padding 4px 12px, border 1px solid #3f3f46, font-size 0.75rem
- Code blocks: background #09090b, border-radius 12px, padding 16px, font-family monospace
- Buttons (primary): background #e4530a, color white, border-radius 8px, padding 10px 20px
- Dividers: border-color #27272a, opacity 0.6

LAYOUT:
- Max content width: 1200px, centered
- Section padding: 48px 24px
- Grid gap: 16-24px
- Always use CSS Grid or Flexbox, never tables for layout

CHARTS (when using Chart.js or similar):
- Background: transparent
- Grid lines: rgba(255,255,255,0.06)
- Tick color: #71717a
- Dataset colors in order: #e4530a, #3b82f6, #22c55e, #a855f7, #f59e0b
- Legend label color: #a1a1aa

Always produce self-contained HTML with all CSS inline or in a <style> tag. No external CSS frameworks unless Chart.js CDN for charts.
```

---

## Use cases

- HTML presentations and reports
- Dashboards and data visualizations
- Any visual output from Cline

## About

Made by [MegaBrain](https://getmegabrain.com) — AI routing for 500+ models.  
More skills: [getmegabrain.com/docs/skills](https://getmegabrain.com/docs/skills)
