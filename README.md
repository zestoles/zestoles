<p align="center">
  <img src="https://raw.githubusercontent.com/zestoles/zestoles/main/assets/kernel-signal.svg" alt="Numerical systems and kernel correctness" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/zestoles"><img src="https://img.shields.io/badge/GitHub-zestoles-0b1220?style=flat-square&logo=github&logoColor=ffffff" alt="GitHub" /></a>
  <a href="https://dev.to/gundi61"><img src="https://img.shields.io/badge/Dev.to-@gundi61-0b1220?style=flat-square&logo=devdotto&logoColor=ffffff" alt="Dev.to" /></a>
  <img src="https://img.shields.io/badge/Focus-numerical%20correctness-0b1220?style=flat-square&logo=target&logoColor=5eead4" alt="Focus: numerical correctness" />
</p>

## About

I work on numerical correctness at the boundary between software and hardware: IEEE 754 behavior, low-level math kernels, and the awkward edge cases hidden in integer and floating-point datapaths.

My approach is deliberately evidence-first: reproduce the failure, trace the data path, model the relevant execution semantics, and validate that a fix improves the affected cases without changing the rest.

<p align="center">
  <img src="https://raw.githubusercontent.com/zestoles/zestoles/main/assets/evidence-loop.svg" alt="Evidence-first numerical debugging workflow" width="100%" />
</p>

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

<p align="center">
  <a href="https://github.com/zestoles/tt-metal"><img src="https://img.shields.io/badge/CONTRIBUTIONS-tt--metal-102947?style=for-the-badge&logo=github&logoColor=5eead4" alt="tt-metal contributions" /></a>
  <a href="https://github.com/zestoles/kernel-audit-playbook"><img src="https://img.shields.io/badge/METHODOLOGY-kernel--audit--playbook-102947?style=for-the-badge&logo=bookstack&logoColor=5eead4" alt="Kernel audit playbook" /></a>
  <a href="https://github.com/zestoles/bounty-watcher"><img src="https://img.shields.io/badge/AUTOMATION-bounty--watcher-102947?style=for-the-badge&logo=githubactions&logoColor=5eead4" alt="Bounty watcher" /></a>
</p>

<p align="center"><sub>Upstream contribution · repeatable methodology · practical automation</sub></p>

## Toolbox

<p>
  <img src="https://img.shields.io/badge/C%2B%2B-0b1220?style=for-the-badge&logo=cplusplus&logoColor=5eead4" alt="C++" />
  <img src="https://img.shields.io/badge/C-0b1220?style=for-the-badge&logo=c&logoColor=5eead4" alt="C" />
  <img src="https://img.shields.io/badge/Python-0b1220?style=for-the-badge&logo=python&logoColor=5eead4" alt="Python" />
  <img src="https://img.shields.io/badge/Git-0b1220?style=for-the-badge&logo=git&logoColor=5eead4" alt="Git" />
  <img src="https://img.shields.io/badge/Linux-0b1220?style=for-the-badge&logo=linux&logoColor=5eead4" alt="Linux" />
  <img src="https://img.shields.io/badge/GitHub_Actions-0b1220?style=for-the-badge&logo=githubactions&logoColor=5eead4" alt="GitHub Actions" />
</p>

## Currently exploring

- Floating-point special values and signed-zero behavior
- Integer boundary cases in accelerator kernels
- Reproducible correctness tooling for numerical software

<p align="center"><sub>Correctness is not negotiable — even at 2<sup>−149</sup>.</sub></p>



