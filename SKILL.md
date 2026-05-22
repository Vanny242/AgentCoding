# UI/UX Pro Max - Design Intelligence

Comprehensive design guide for web and mobile applications. Contains 50+ styles, 161 color palettes, 57 font pairings, 161 product types with reasoning rules, 99 UX guidelines, and 25 chart types across 10 technology stacks. Searchable database with priority-based recommendations.

## Rule Categories by Priority

| Priority | Category | Impact | Domain | Key Checks (Must Have) | Anti-Patterns (Avoid) |
|----------|----------|--------|--------|------------------------|------------------------|
| 1 | Accessibility | CRITICAL | `ux` | Contrast 4.5:1, Alt text, Keyboard nav, Aria-labels | Removing focus rings, Icon-only buttons without labels |
| 2 | Touch & Interaction | CRITICAL | `ux` | Min size 44×44px, 8px+ spacing, Loading feedback | Reliance on hover only, Instant state changes (0ms) |
| 3 | Performance | HIGH | `ux` | WebP/AVIF, Lazy loading, Reserve space (CLS < 0.1) | Layout thrashing, Cumulative Layout Shift |
| 4 | Style Selection | HIGH | `style`, `product` | Match product type, Consistency, SVG icons (no emoji) | Mixing flat & skeuomorphic randomly, Emoji as icons |
| 5 | Layout & Responsive | HIGH | `ux` | Mobile-first breakpoints, Viewport meta, No horizontal scroll | Horizontal scroll, Fixed px container widths, Disable zoom |
| 6 | Typography & Color | MEDIUM | `typography`, `color` | Base 16px, Line-height 1.5, Semantic color tokens | Text < 12px body, Gray-on-gray, Raw hex in components |
| 7 | Animation | MEDIUM | `ux` | Duration 150–300ms, Motion conveys meaning, Spatial continuity | Decorative-only animation, Animating width/height, No reduced-motion |
| 8 | Forms & Feedback | MEDIUM | `ux` | Visible labels, Error near field, Helper text, Progressive disclosure | Placeholder-only label, Errors only at top, Overwhelm upfront |
| 9 | Navigation Patterns | HIGH | `ux` | Predictable back, Bottom nav ≤5, Deep linking | Overloaded nav, Broken back behavior, No deep links |
| 10 | Charts & Data | LOW | `chart` | Legends, Tooltips, Accessible colors | Relying on color alone to convey meaning |

---

## Core Guidelines Applied to index1.html

### 1. Bento Grid (便當盒網格) 佈局
- 在大螢幕上，首頁資訊會以現代的便當盒網格呈現：
  - 個人簡介區塊 (佔據左上方 2x2)。
  - GitHub Stats 看板 (佔據右上方 2x1)。
  - 技術棧雷達與語言分佈 (佔據右中 2x1)。
  - 專案儲存庫格線 (排列在下方 3xN Grid)。
- 在行動端上自動崩解，轉化為 Mobile-first 垂直排列流。

### 2. 進階互動體驗 (Touch & Interaction)
- 點擊卡片與按鈕擁有細緻的回彈縮放動畫 (`scale(0.98)` / `transition: all 0.2s cubic-bezier(0.16, 1, 0.3, 1)`)。
- 所有可點擊元素都設置 `cursor: pointer` 並確保觸控目標大於 `44x44px`。
- 所有 Icon 按鈕均有 `aria-label` 提供輔助技術讀取。

### 3. 微動畫 (Micro-animations)
- 網格項目在載入時使用 **Stagger Sequence (交錯序列)** 動畫淡入（間隔 `40ms`），展現極高的流暢度。
- 背景擁有流暢運作的霓虹光點動畫。
