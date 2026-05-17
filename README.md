<!-- SPDX-License-Identifier: CC-BY-4.0 -->
# `openexam-demo-library`

A shared library of OpenExam assignments and an institutional design, used by the [`openexam-demo-cs101`](https://github.com/ArneKummerow/openexam-demo-cs101) demo course.

## Layout

```
.
├── designs/
│   └── institutional.design     LaTeX preamble + HTML/CSS theming
└── assignments/
    ├── units/
    │   ├── bits-to-bytes.assign        mc, 1 pt
    │   └── memory-units.assign         cloze, 2 pt
    ├── numbers/
    │   ├── powers-of-two.assign        numeric, 1 pt
    │   ├── twos-complement.assign      numeric, 2 pt
    │   └── endianness.assign           truefalse, 1 pt
    ├── instructions/
    │   ├── match-isa.assign            match, 3 pt
    │   └── explain-cache.assign        freetext, 4 pt
    └── code/
        ├── mac-address-regex.assign    regex, 2 pt
        └── hello-world.assign          code (Python), 2 pt
```

## Versioning

Stable tags (`v1`, `v2`, …) pin specific revisions consumers can reference. Downstream `.test` and `.template` files should `@tag:v1` (or similar) rather than referencing the working tree, so an exam built today is reproducible months later.

## License

Content is **CC-BY-4.0** (see frontmatter `license:` on each file and per-file SPDX headers).
