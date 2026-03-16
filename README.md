# Sorting Algorithms — Interactive Visualizations

A single-file, zero-dependency interactive guide to **10 classic sorting algorithms**, each with its own unique visualization that reflects how the algorithm actually works. Built with vanilla HTML, CSS, and JavaScript.

![Sorting Algorithms Preview](https://img.shields.io/badge/algorithms-10-7c6fe0?style=flat-square) ![Examples](https://img.shields.io/badge/examples%20per%20algo-5-00c9a7?style=flat-square) ![Dependencies](https://img.shields.io/badge/dependencies-none-22c55e?style=flat-square) ![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)

---

## Live Demo

Just open `sorting-algorithms.html` in any modern browser — no build step, no server, no install required.

---

## What's Inside

### 10 Algorithms Covered

| Algorithm | Type | Best | Average | Worst | Space | Stable |
|-----------|------|------|---------|-------|-------|--------|
| Bubble Sort | Comparison · In-Place | O(n) | O(n²) | O(n²) | O(1) | ✓ |
| Selection Sort | Comparison · In-Place | O(n²) | O(n²) | O(n²) | O(1) | ✗ |
| Insertion Sort | Comparison · In-Place | O(n) | O(n²) | O(n²) | O(1) | ✓ |
| Shell Sort | Comparison · In-Place | O(n log n) | O(n log²n) | O(n²) | O(1) | ✗ |
| Merge Sort | Divide & Conquer | O(n log n) | O(n log n) | O(n log n) | O(n) | ✓ |
| Quick Sort | Divide & Conquer | O(n log n) | O(n log n) | O(n²) | O(log n) | ✗ |
| Heap Sort | Comparison · In-Place | O(n log n) | O(n log n) | O(n log n) | O(1) | ✗ |
| Counting Sort | Non-Comparison · Integer | O(n+k) | O(n+k) | O(n+k) | O(k) | ✓ |
| Bucket Sort | Non-Comparison · Distribution | O(n+k) | O(n+k) | O(n²) | O(n+k) | ✓ |
| Radix Sort | Non-Comparison · Digit | O(d(n+k)) | O(d(n+k)) | O(d(n+k)) | O(n+k) | ✓ |

---

## Unique Visualizations

Each algorithm has a visualization designed to match how it actually works — not a generic bar chart for all of them.

### Bubble Sort — Proportional Bar Chart
Bar height is proportional to element value (taller bar = larger number). Amber bars = currently comparing, Red = swapping, Green = final sorted position. An element row below the bars shows the same state.

### Selection Sort — Boundary + Scan Line
Large element boxes with a moving `▶` boundary marker separating the sorted (green) and unsorted regions. An `MIN` pointer tracks the current minimum found during each scan. Pointer labels align precisely below each element.

### Insertion Sort — Card Hand & Deck
The sorted portion is displayed as a green **hand of cards** on the left. The remaining unsorted elements form the **deck** on the right. The key card being inserted is shown in purple as it slides left through the hand, shifting amber cards right to make room.

### Shell Sort — Gap Groups
All elements are shown in a row. Below, elements that belong to the same gap-group are clustered together with colored brackets connecting them. Each gap-group has its own color. Comparing and swapping pairs are highlighted in amber/red within their group.

### Merge Sort — Level-by-Level Tree
Shows all merge levels stacked top to bottom: `atoms → groups of 2 → groups of 4 → sorted`. Split phase highlights which segment is being divided (blue). Merge phase shows segments turning amber as they are being merged, then green once complete — progress flows **downward** from atoms to fully sorted.

### Quick Sort — Three-Zone Partition
The active partition is split into three labeled zones displayed in real time:
- **Blue zone** — elements ≤ pivot
- **Pink zone** — the pivot (in its final sorted position after placement)
- **Orange zone** — elements > pivot

The full array row above shows the current state with the comparing element highlighted in amber.

### Heap Sort — SVG Binary Tree with Edges
The heap is drawn as an actual binary tree using SVG, with **edge lines connecting parent nodes to their children**. Node positions are calculated mathematically per tree level. Purple nodes = in heap, Amber = comparing, Red = swapping. Extracted sorted elements are shown in a separate green row below the tree.

### Counting Sort — Tally Chart + Variables
Displays `n` (array size) and `k` (max value) as labeled variable badges at the top along with the computed `O(n+k)` value. Three sections update step by step: the input array (amber = currently counting), a **tally bar chart** for `count[0..k]` (bars change color per phase: blue=counting, purple=prefix sum, teal=output placement), and an output array that fills in one slot at a time right-to-left for stability.

### Bucket Sort — Physical Colored Buckets
Each of the `√n` buckets is drawn as a colored container labeled with its value range. Elements are colored to match the bucket they belong to. Buckets fill up during the distribution phase, then are sorted individually and concatenated in order.

### Radix Sort — Digit Buckets with d, n, k Variables
Shows `d` (digit count), `n` (array size), and `k = 10` (base) as variable badges with the computed `O(d(n+k))` value. Each number in the array is displayed with the **currently active digit highlighted** in amber. Ten labeled digit buckets (0–9) are shown filling up during each pass, then being read back in order.

---

## Features

- **Step-by-step control** — step forward and backward through every single operation
- **Auto-play** — watch the algorithm run at adjustable speed
- **5 preset examples per algorithm** — including best-case (already sorted), worst-case (reverse sorted), duplicates, and random arrays
- **Algorithm info panel** — description, how-it-works steps, complexity table, stability, and a visualization guide for each algorithm
- **Color-coded legend** — each visualization has its own legend explaining what each color means
- **Progress bar** — shows how far through the step sequence you are
- **Mobile responsive** — single-column layout on small screens, horizontally scrollable tabs, touch-friendly controls

---

## Project Structure

```
sorting-algorithms/
└── sorting-algorithms.html     # Entire project — one self-contained file
```

No build tools, no frameworks, no external CDN calls. Everything runs locally from the single HTML file.

---

## How to Use

**1. Clone or download**
```bash
git clone https://github.com/your-username/sorting-algorithms.git
cd sorting-algorithms
```

**2. Open in browser**
```bash
# Just open the file directly
open sorting-algorithms.html

# Or serve it locally (optional)
python -m http.server 8080
# then visit http://localhost:8080/sorting-algorithms.html
```

**3. Navigate**
- Click any algorithm tab at the top to switch algorithms
- Click **Ex 1–5** to switch between example arrays
- Use **◀ Prev** / **Next ▶** to step through manually
- Click **▶▶ Auto** for automatic playback — drag the speed slider to adjust
- Click **↺** to restart the current example from the beginning

---

## Color Reference

All visualizations share a consistent dark theme color system:

| Color | Meaning |
|-------|---------|
| 🟡 Amber `#f59e0b` | Elements currently being compared |
| 🔴 Red `#ef4444` | Elements being swapped or moved |
| 🟢 Green `#22c55e` | Elements in their final sorted position |
| 🩷 Pink `#ec4899` | Pivot element (Quick Sort) |
| 🟣 Purple `#a855f7` | Nodes currently in the heap (Heap Sort) |
| 🔵 Blue `#4f7ef7` | Elements ≤ pivot zone / split phase |
| 🟠 Orange `#f97316` | Elements > pivot zone / minimum marker |
| 🩵 Teal `#14b8a6` | Element being placed into output position |

---

## Implementation Notes

All 10 step generators are pure functions that take an input array and return an array of step objects. Each step captures a snapshot of the array state plus metadata for the renderer (which indices are comparing, swapping, sorted, etc.). The renderer for each algorithm is completely independent — no shared rendering code between algorithms.

```
genBubble(arr)    → Step[]    (bar chart renderer)
genSelection(arr) → Step[]    (boundary + pointer renderer)
genInsertion(arr) → Step[]    (card hand renderer)
genShell(arr)     → Step[]    (gap group renderer)
genMerge(arr)     → Step[]    (level tree renderer)
genQuick(arr)     → Step[]    (three-zone renderer)
genHeap(arr)      → Step[]    (SVG tree renderer)
genCounting(arr)  → Step[]    (tally chart renderer)
genBucket(arr)    → Step[]    (bucket renderer)
genRadix(arr)     → Step[]    (digit bucket renderer)
```

---

## Browser Support

Works in all modern browsers. No polyfills required.

| Browser | Supported |
|---------|-----------|
| Chrome 90+ | ✓ |
| Firefox 88+ | ✓ |
| Safari 14+ | ✓ |
| Edge 90+ | ✓ |
| Mobile Chrome / Safari | ✓ |

---

## Contributing

Pull requests are welcome! Some ideas for contributions:

- Add more example arrays (very large inputs, already-sorted, all-same-value edge cases)
- Add a comparison mode to run two algorithms side-by-side
- Add audio feedback (tone pitch proportional to element value — a classic!)
- Add a custom input field so users can sort their own arrays
- Add time and swap counters per step

---

## Author

Built by [Induwara Uthsara](https://induwara.dev) — Full-Stack Developer & Microsoft Learn Student Ambassador (Beta), Sri Lanka.

- Portfolio: [induwara.dev](https://induwara.dev)
- Blog: [blog.induwara.dev](https://blog.induwara.dev)
- GitHub: [@your-username](https://github.com/your-username)

---

## License

MIT License — free to use, modify, and distribute. See [LICENSE](LICENSE) for details.

---

> Made for learning. Every algorithm has been chosen to show that there is no single best sorting algorithm — each one has a scenario where it shines.