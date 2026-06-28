# Analysis Pages — Screenshot Guide

This explains how the three Analysis pages use screenshots, so anyone editing
them stays consistent. The Analysis section is built from **screenshots of the
Shiny app**, not live R code — the app is the source of truth, the website
documents the findings.

If you change a chart in the Shiny app, **re-take its screenshot and replace the
file** (keep the same filename). The page text may also need a small update if
the chart's numbers or message changed.

---

## Where things live

- The three pages are at the repo root: `analysis-overview.qmd`,
  `analysis-attack-chain.qmd`, `analysis-intervention.qmd`.
- All screenshots go in a single `images/` folder at the repo root.
- Each page references its images by relative path, e.g. `images/tab1-org-chart.png`.

If `images/` doesn't exist yet, create it and drop the PNGs in.

---

## Naming convention

Filenames follow `tab{N}-{short-description}.png`, all lowercase, words joined
by hyphens. The `tab{N}` prefix says which Shiny tab the screenshot came from.
**Use these exact names** — the pages already point at them, so a mismatch shows
a broken-image icon.

### Page 1 — `analysis-overview.qmd` (Tab 1: System Overview)
| File | What to capture |
| --- | --- |
| `images/tab1-kpi-boxes.png` | The four KPI info-boxes (Total Events / Worm Relays / Anomalous Posts / Departments Touched) |
| `images/tab1-org-chart.png` | The org chart, collapsed to departments (or expanded one level) |
| `images/tab1-daily-volume.png` | The Daily Event Volume area chart with the three campaign markers |
| `images/tab1-post-attribution.png` | The SaidIT Post Attribution stacked bar |
| `images/tab1-permission-surface.png` | The SaidIT Permission Surface bar chart, "All Departments" view |
| `images/tab1-posting-time.png` | The Posting Time Distribution chart |

### Page 2 — `analysis-attack-chain.qmd` (Tab 2: Attack Chain)
| File | What to capture |
| --- | --- |
| `images/tab2-propagation-network.png` | The Worm Propagation Network, "All Campaigns" view |
| `images/tab2-relay-table.png` | The Relay Chain sender/receiver table, first page |
| `images/tab2-self-loops.png` | The Self-Loop Detection Signal chart |
| `images/tab2-dept-heatmap.png` | The Department-Level Contamination Heatmap |

> Note: the five-event attack sequence is **written directly into the page as
> text** (it was pure text, so no screenshot is needed). Don't add a screenshot
> for it.

### Page 3 — `analysis-intervention.qmd` (Tabs 3 & 4: Campaign History + Intervention)
| File | What to capture |
| --- | --- |
| `images/tab3-campaign-timeline.png` | The Campaign Timeline |
| `images/tab3-comparison-table.png` | The Campaign Comparison Table |
| `images/tab3-velocity-density.png` | The Relay Velocity Density plot |
| `images/tab3-agent-overlap.png` | The Agent Overlap Across Campaigns chart |
| `images/tab3-relay-calendar.png` | The Relay Activity Calendar |
| `images/tab4-intervention-layers.png` | The three-layer Intervention Design cards |
| `images/tab4-decision-matrix.png` | The Intervention Decision Matrix table |

---

## Adding a screenshot in the page (if you add a new chart)

Each image is inserted with standard Markdown plus a caption and alt text:

```markdown
![Caption shown under the image.](images/tab2-new-chart.png){#fig-newchart fig-alt="Plain-language description for accessibility."}
```

Then add a short **"What it shows"** paragraph under it explaining the finding —
that's the pattern every chart on these pages follows: image, then one paragraph
of interpretation.
