<!-- SPDX-License-Identifier: CC-BY-4.0 -->
# openexam-demo-library

A reusable bank of `.oex` questions, designed to be `<import>`-ed from another `.oex`. This is one of two repos in the OpenExam end-to-end demo; the other is [`openexam-demo-course`](../course/), which imports from here to build a midterm exam.

## Layout

```
questions/
├── velocity-mc.oex       # multipleChoice — canonical form (no sugar)
├── vectors-mc.oex        # multipleChoice — [x] / [ ] shorthand
├── scheduling-mc.oex     # multipleChoice — (x) / ( ) parens shorthand + oneWrongMinusOne
├── projectile.oex        # frontmatter params + expression slots ({params.mass + params.velocity})
├── kinematics-cloze.oex  # clozeFill with mixed numeric + string <blank/> markers
├── cidr-regex.oex        # regexMatch with pattern + flags
├── unix-match.oex        # matchPairs — `- left -> right` shorthand
├── osi-match.oex         # matchPairs — canonical <pair left=... right=.../>
└── ethics.oex            # trueFalse + freeText (keywords + expected modes)
```

## Spec coverage

Each file's frontmatter declares `spec: openexam/2`. Between them the questions exercise:

- All 8 first-party addons (`multipleChoice`, `trueFalse`, `numericInput`, `freeText`, `regexMatch`, `clozeFill`, `matchPairs`, `codeRunner` — except `codeRunner`, since auto-running is deferred per [`spec/addon.md`](../../spec/addon.md) §16).
- Canonical-form and shorthand-form for every addon that has a `transformBody` hook.
- Frontmatter params with `int(default=...)` inferred-type sugar and explicit `range(...)` / `oneOf(...)` constructors.
- Expression slots `{...}` referencing `params`, the built-in `student`, `seed`, and `date` globals.
- Per-question `points=` + per-child `points=` for non-uniform scoring.

## License

Apache-2.0 — see the workspace root LICENSE.
