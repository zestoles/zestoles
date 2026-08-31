# Görkem TUNA

> **NUMERICAL SYSTEMS / KERNEL CORRECTNESS**
>
> `IEEE 754` · `edge cases` · `reproducible evidence`

`GitHub: zestoles` · `Dev.to: @gundi61` · `Focus: numerical correctness + responsible disclosure`

## About

I work on numerical correctness at the boundary between software and hardware: IEEE 754 behavior, low-level math kernels, and the awkward edge cases hidden in integer and floating-point datapaths.

My approach is deliberately evidence-first: reproduce the failure, trace the data path, model the relevant execution semantics, and validate that a fix improves the affected cases without changing the rest.

Alongside upstream work, I participate in responsible disclosure and public bug-bounty programs, including HackerOne and Bugcrowd. I report findings privately, keep scope and program rules first, and disclose technical detail only through the approved process.

## Evidence-first workflow

```text
01 / REPRODUCE  →  02 / MODEL  →  03 / VALIDATE  →  04 / UPSTREAM
minimal failing     trace the path     strict improvement    small, clear patch
input + reference   bits + semantics   no collateral change  focused regression
```

## Selected work

| Area | What I do |
| --- | --- |
| **Kernel correctness** | Bit-exact reference models for SFPU/SIMD-style numerical behavior, compared against trusted implementations. |
| **Low-level debugging** | Source-level root-cause analysis across architecture-specific kernel copies and numeric-conversion branches. |
| **Regression design** | Small, adversarial tests for special values and boundary conditions that ordinary random testing misses. |

### Merged upstream contribution

[`tenstorrent/tt-metal#54240`](https://github.com/tenstorrent/tt-metal/pull/54240) — fixed an IEEE 754 special case in `ttnn.atan2` where `atan2(±∞, ±0)` returned `0` or `π` instead of `±π/2`.

- Approved by three engineers and merged upstream.
- Fix covers all affected architecture copies and adds a focused special-values regression test.
- Read the technical write-up: [How I Found an IEEE 754 Violation in an AI Chip Company's Math Kernel](https://dev.to/gundi61/how-i-found-an-ieee-754-violation-in-an-ai-chip-companys-math-kernel-524o).

## Project shelf

- [`tt-metal`](https://github.com/zestoles/tt-metal) — upstream contributions to numerical kernels
- [`kernel-audit-playbook`](https://github.com/zestoles/kernel-audit-playbook) — repeatable numerical-audit methodology
- [`bounty-watcher`](https://github.com/zestoles/bounty-watcher) — cautious public-opportunity triage automation

## Toolbox

`C++` · `C` · `Python` · `Git` · `Linux` · `GitHub Actions`

## Currently exploring

- Floating-point special values and signed-zero behavior
- Integer boundary cases in accelerator kernels
- Reproducible correctness tooling for numerical software

<p align="center"><sub>Correctness is not negotiable — even at 2<sup>−149</sup>.</sub></p>





