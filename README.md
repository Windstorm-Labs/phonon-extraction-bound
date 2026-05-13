# Paper 10: Phonon Extraction Bound — Experiments & Code

**A Non-Equilibrium Efficiency Bound for Phonon Extraction in Bose–Einstein Condensate Analog Gravity Systems with Numerical Tests of the Underlying Thermodynamic Assumption**

[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20014391-blue)](https://doi.org/10.5281/zenodo.20014391)
[![License: MIT](https://img.shields.io/badge/Code-MIT-green)](https://opensource.org/licenses/MIT)
[![License: CC BY 4.0](https://img.shields.io/badge/Data-CC_BY_4.0-lightgrey)](https://creativecommons.org/licenses/by/4.0/)
[![Track: Entropic Bounds](https://img.shields.io/badge/Track-2_·_Entropic_Bounds-8b5cf6)](https://windstorminstitute.org/#track2)

> **First paper of the Windstorm Institute's Track 2 — Entropic Bounds in Analog Systems.** A separate research line from the throughput-basin arc (Papers 1–9), sharing the same Clausius-inequality / entropy-production lens applied to a different substrate.

---

## Published Paper

- **[Windstorm-Institute/phonon-extraction-bound](https://github.com/Windstorm-Institute/phonon-extraction-bound)** — paper PDF, article HTML, submission scaffolds
- **Website article:** [windstorminstitute.org/articles/phonon-extraction-bound.html](https://windstorminstitute.org/articles/phonon-extraction-bound.html)
- **Zenodo:** [10.5281/zenodo.20014391](https://doi.org/10.5281/zenodo.20014391) (deposited 2026-05-03)

## What this repo will hold

The paper's Section 3 numerical evidence consists of five independent QuTiP Lindblad master-equation tests of the load-bearing thermodynamic substitution `δQ = T · dS` (Assumption A in §2.3). When the experiment scripts and raw output logs are mirrored here, this directory will contain:

| Test | Directory | Probes | Outcome (per paper §3) |
|------|-----------|--------|------------------------|
| 1 — Single-qubit baseline | `experiments/test1_qubit_timestep/` | Timestep convergence (`dt` → 0) | ✓ *O(dt)* for `r ≥ 0.20` |
| 2 — Bosonic mode | `experiments/test2_bosonic_mode/` | Truncated harmonic oscillator (N = 10) | ✓ matches qubit, indistinguishable |
| 3 — Strong coupling | `experiments/test3_strong_coupling/` | `γ/ω` swept 0.05 → 2.0 | ✓ for `r ≥ 0.30` |
| 4 — Two-bath NESS | `experiments/test4_twobath_ness/` | Driven non-equilibrium steady state | ✓ exact to `~10⁻¹⁶` |
| 5 — Coherent initial state | `experiments/test5_coherent_state/` | Non-thermal `\|+⟩` superposition | ✗ fails — clean scope limit |

**Convergence diagnostics, raw output logs, and the master notebook reproducing the paper's §3 tables** will live alongside each script.

## Code archive (current authoritative source)

> **Note (May 2026):** The full simulation source — including raw output logs, convergence-order analyses, and intermediate working drafts — is archived alongside the paper on **[Zenodo (10.5281/zenodo.20014391)](https://doi.org/10.5281/zenodo.20014391)**. Mirroring to this repo is in progress; until that completes, the Zenodo deposit is the canonical reproducibility archive.

## Reproduction (when scripts are mirrored)

- **Library:** QuTiP 5.2.3 (or compatible)
- **Python:** 3.12+
- **Total compute:** ~30 minutes on a standard CPU (no GPU required)
- **No external data:** all inputs are analytic; all outputs are deterministic given seeded RNG

## Hardware

The published numerics were executed by code-execution-enabled large-language-model instances (Claude, Grok, Gemini, ChatGPT, Perplexity) running real Python in sandboxed environments — see the paper's *Methodology Note*. No GPU was required; the simulations are small Lindblad-equation integrations (single-qubit and N=10 bosonic-mode systems).

---

## Discuss this code

- **Bug, reproduction failure, or unexpected output?** → [Open an Issue](../../issues)
- **Q&A — version compatibility, hardware, generalization to other inputs?** → [Start a Discussion](../../discussions)
- **Discuss the paper itself** → [Comments on the website article](https://windstorminstitute.org/articles/phonon-extraction-bound.html#comments) or [Issues on the Institute repo](https://github.com/Windstorm-Institute/phonon-extraction-bound/issues)

---

## The Windstorm Institute

### Track 1 — The Throughput Basin · 9 papers (Papers 1–9 globally; 1st through 9th in this track; arc complete)

| # | Paper | DOI |
|---|-------|-----|
| 1 | [The Fons Constraint](https://github.com/Windstorm-Institute/fons-constraint) | [10.5281/zenodo.19274048](https://doi.org/10.5281/zenodo.19274048) |
| 2 | [The Receiver-Limited Floor](https://github.com/Windstorm-Institute/receiver-limited-floor) | [10.5281/zenodo.19322973](https://doi.org/10.5281/zenodo.19322973) |
| 3 | [The Throughput Basin](https://github.com/Windstorm-Institute/throughput-basin) | [10.5281/zenodo.19323194](https://doi.org/10.5281/zenodo.19323194) |
| 4 | [The Serial Decoding Basin τ](https://github.com/Windstorm-Institute/serial-decoding-basin) | [10.5281/zenodo.19323423](https://doi.org/10.5281/zenodo.19323423) |
| 5 | [The Dissipative Decoder](https://github.com/Windstorm-Institute/dissipative-decoder) | [10.5281/zenodo.19433048](https://doi.org/10.5281/zenodo.19433048) |
| 6 | [The Inherited Constraint](https://github.com/Windstorm-Institute/inherited-constraint) | [10.5281/zenodo.19432911](https://doi.org/10.5281/zenodo.19432911) |
| 7 | [The Throughput Basin Origin](https://github.com/Windstorm-Institute/throughput-basin-origin) | [10.5281/zenodo.19498582](https://doi.org/10.5281/zenodo.19498582) |
| 8 | [The Vision Basin](https://github.com/Windstorm-Institute/vision-basin) | [10.5281/zenodo.19672827](https://doi.org/10.5281/zenodo.19672827) |
| 9 | [The Hardware Basin](https://github.com/Windstorm-Institute/hardware-basin) | [10.5281/zenodo.19672921](https://doi.org/10.5281/zenodo.19672921) |

### Track 2 — Entropic Bounds in Analog Systems · 7 papers (Papers 10–16 globally; 1st through 4th in this track; line of inquiry active)

| # | Paper | DOI |
|---|-------|-----|
| 10 | [Phonon Extraction Bound (BEC Analog Gravity)](https://github.com/Windstorm-Institute/phonon-extraction-bound) *(this paper — 1st in track)* | [10.5281/zenodo.20014391](https://doi.org/10.5281/zenodo.20014391) |
| 11 | [Gravitational Entropy Escrow](https://github.com/Windstorm-Institute/gravitational-entropy-escrow) *(2nd in track)* | [10.5281/zenodo.20032023](https://doi.org/10.5281/zenodo.20032023) |
| 12 | [C8 Clarification Note](https://github.com/Windstorm-Institute/c8-clarification-note) *(3rd in track; companion to Paper 11)* | [10.5281/zenodo.20041992](https://doi.org/10.5281/zenodo.20041992) |

| 13 | [Lattice QFT Test of the Static Escrow Postulate](https://github.com/Windstorm-Institute/lattice-qft-test) *(4th in track; supplement to Paper 11)* | [10.5281/zenodo.20057538](https://doi.org/10.5281/zenodo.20057538) |
| 14 | [Spacetime as Escrow Bookkeeping](https://github.com/Windstorm-Institute/escrow-spacetime) *(5th in track; translation of standard GR results into the escrow vocabulary; companion to Paper 11)* | [10.5281/zenodo.20126091](https://doi.org/10.5281/zenodo.20126091) |
| 15 | [The 𝒩<sub>esc</sub> Recipe](https://github.com/Windstorm-Institute/nesc-recipe) *(6th in track; formalizes 𝒩<sub>esc</sub> as a cross-regime function; continuation of Paper 14)* | [10.5281/zenodo.20145106](https://doi.org/10.5281/zenodo.20145106) |
| 16 | [The Compton Corollary](https://github.com/Windstorm-Institute/compton-corollary) | [10.5281/zenodo.20163451](https://doi.org/10.5281/zenodo.20163451) | [Labs](https://github.com/Windstorm-Labs/compton-corollary) |
**Website:** [windstorminstitute.org](https://windstorminstitute.org)

---

*Code: MIT License · Data: CC BY 4.0*
