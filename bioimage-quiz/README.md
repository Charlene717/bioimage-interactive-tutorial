# Bioimage Analysis · Interactive Quiz

A bilingual (zh / en) self-test module covering the 13 topics in `../`. ~130 questions across single-choice / multi-select / true-false types.

## Files

- `index.html` — quiz UI: subject index, per-question view, sidebar grid, progress
- `data.js` — question bank (`window.QUIZ_DATA.bioimage`)
- `i18n.js` — language toggle (storage key: `bioimage_quiz_lang`)
- Imports shared styles from `../i18n.js` for language consistency

## Question schema (`data.js`)

```js
{
  type: "single" | "multi" | "tf",
  stem: "中文題幹...",        stem_en: "English stem...",
  A:    "中文選項 A",          A_en:    "Option A",
  // B, C, D similarly (omit for tf)
  ans:  "A"  | ["A","C"] | "T",
  exp:  "中文解析",            exp_en:  "English explanation"
}
```

`window.QUIZ_DATA.bioimage` has the structure:

```
{
  label, label_en, labels_en: { 主題名: "English name", ... },
  subjects: {
    "核心分析流程": {
      "Step 1：影像基礎 (Fundamentals)": [ ...questions... ],
      ...
    },
    "進階主題": {
      "Advanced：3D 與多維分析": [ ...questions... ],
      ...
    }
  }
}
```

## Progress storage

Per-subject progress is stored in `localStorage` under key `bioimage_quiz_progress_v1`:

```js
{
  "<category>||<subject>": {
    ans: {
      0: { sel: ["B"], correct: true,  t: <timestamp> },
      3: { sel: ["A","C"], correct: false, t: <timestamp> }
    }
  }
}
```

Reset is available per-subject and globally from the UI.

## Adding a new question / subject

1. To add **questions to an existing subject**: append a new object to that subject's array in `data.js`.
2. To add a **new subject**: add a new key under the appropriate category (`核心分析流程` or `進階主題`) and (recommended) add the corresponding English label to `labels_en`.
3. Open `index.html` and confirm the new subject appears in the index page with its question count.
