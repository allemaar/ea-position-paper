# Elastic Automators: A Diagnostic Vocabulary for Language-Model-Driven Workflow Systems

> A position paper arguing that many deployed language-model-driven systems are better described as *elastic automation* than as artificial minds — and proposing a diagnostic vocabulary to replace metaphysical inquiries with practical engineering ones.

**Author:** Alexandru Mares — [allemaar.com](https://allemaar.com)
**ORCID:** [0009-0009-6713-9780](https://orcid.org/0009-0009-6713-9780)
**Version:** 0.12.0 (release candidate)
**Status:** Pre-Zenodo deposit
**License:** [CC-BY-4.0](LICENSE)

<!-- Badges populate at v1.0.0 release:
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)
[![arXiv](https://img.shields.io/badge/arXiv-XXXX.XXXXX-b31b1b.svg)](https://arxiv.org/abs/XXXX.XXXXX)
-->

---

## Abstract

We argue that many deployed language-model-driven systems are better described as **elastic automation** than as artificial minds. Traditional automation was rigid by design: rules fired when conditions were met, scripts followed predefined branches, and workflows moved only inside the shapes their designers had imagined. Language models did not need to produce minds to change this arrangement. They gave automation a flexible interface to natural language, allowing software to interpret messy input, classify intent, call tools, retry failed steps, and present coherent outputs to human users. None of this requires explaining the system as knowing in the way a human knows; it only requires the system to produce, in coherent sequence, the kind of output a knowing system would produce. The workflow became less brittle. The input boundary became softer. The automation became elastic.

We define an **elastic automator** as a system that uses a language model to turn uncertain human input into executable structure, then loops through generation, evaluation, correction, and presentation until the output appears intelligent. We argue that treating these systems as artificial minds creates a category error with design consequences, and propose a diagnostic frame: five loop questions that replace metaphysical inquiries about what these systems "know" or "decide" with practical engineering ones. Our contribution is not the underlying observation, which is well-established in practitioner literature. It is the public-facing vocabulary, the lineage from rigid to elastic, and the diagnostic loop questions as a design framework. Naming changes design.

---

## Read

- **Paper (Markdown source):** [`paper.md`](paper.md)
- **Paper (PDF):** `paper.pdf` *(rendered at v1.0.0 tag)*
- **Figures:** [`figures/`](figures/)
- **Changelog:** [`changelog.md`](changelog.md)

### Figures

| # | Title | File |
|---|---|---|
| 1 | The Elastic Automator Loop | [`figures/fig1-elastic-loop.png`](figures/fig1-elastic-loop.png) |
| 2 | The Rigid → Elastic → Agentic Spectrum | [`figures/fig2-rigid-elastic-agentic.png`](figures/fig2-rigid-elastic-agentic.png) |

---

## Cite

```bibtex
@misc{mares2026elastic,
  author       = {Mares, Alexandru},
  title        = {Elastic Automators: A Diagnostic Vocabulary
                  for Language-Model-Driven Workflow Systems},
  year         = {2026},
  publisher    = {Zenodo},
  version      = {0.12.0},
  note         = {DOI assigned at v1.0.0 release}
}
```

GitHub also renders a "Cite this repository" button from [`CITATION.cff`](CITATION.cff).

---

## Status

This is a **release candidate**. The paper text is complete; final-pass items before v1.0.0:

- [ ] Render `paper.pdf`
- [ ] Lossless-optimize figures with `oxipng -o max --strip safe figures/*.png`
- [ ] Tag `v1.0.0`
- [ ] Flip repo public
- [ ] Enable Zenodo GitHub integration → automatic DOI mint
- [ ] Submit to arXiv (cs.AI primary, cs.CY cross-list) with Zenodo DOI in comments

---

## Reproduce

This is a position paper. There is no code or data to reproduce; the contribution is conceptual (vocabulary, lineage, diagnostic loop questions).

---

## License

Paper text and figures: [CC-BY-4.0](LICENSE). Any code in subdirectories: MIT, unless stated otherwise.
