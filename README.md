# Elastic Automators: A Diagnostic Vocabulary for Language-Model-Driven Workflow Systems

> A position paper arguing that many deployed language-model-driven systems are better described as *elastic automation* than as artificial minds — and proposing a diagnostic vocabulary to replace metaphysical inquiries with practical engineering ones.

**Author:** Alexandru Mares — [allemaar.com](https://allemaar.com)
**ORCID:** [0009-0009-6713-9780](https://orcid.org/0009-0009-6713-9780)
**Version:** 1.0.0
**Status:** Published — 2026-04-27
**License:** [CC-BY-4.0](LICENSE)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19802018.svg)](https://doi.org/10.5281/zenodo.19802018)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

**Zenodo:** [zenodo.org/records/19802018](https://zenodo.org/records/19802018)
**Concept DOI** (always resolves to latest version): [10.5281/zenodo.19802017](https://doi.org/10.5281/zenodo.19802017)

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

**APA:**

> Mares, A. (2026). *Elastic Automators: A Diagnostic Vocabulary for Language-Model-Driven Workflow Systems* (Version 1.0.0) [Preprint]. Zenodo. https://doi.org/10.5281/zenodo.19802018

**BibTeX:**

```bibtex
@misc{mares2026elastic,
  author       = {Mares, Alexandru},
  title        = {Elastic Automators: A Diagnostic Vocabulary
                  for Language-Model-Driven Workflow Systems},
  year         = {2026},
  month        = apr,
  publisher    = {Zenodo},
  version      = {1.0.0},
  doi          = {10.5281/zenodo.19802018},
  url          = {https://doi.org/10.5281/zenodo.19802018}
}
```

GitHub also renders a "Cite this repository" button from [`CITATION.cff`](CITATION.cff).

---

## Status

**Published as Zenodo preprint v1.0.0 on 2026-04-27.** DOI: [10.5281/zenodo.19802018](https://doi.org/10.5281/zenodo.19802018).

- [x] Render `paper.pdf`
- [x] Manual deposit to Zenodo → DOI minted
- [x] Tag `v1.0.0`
- [x] Flip repo public
- [ ] Lossless-optimize figures with `oxipng -o max --strip safe figures/*.png` *(optional, not blocking)*
- [ ] Submit to arXiv *(deferred — Zenodo DOI is the authoritative deposit; arXiv may follow when endorsement path is natural)*

---

## Reproduce

This is a position paper. There is no code or data to reproduce; the contribution is conceptual (vocabulary, lineage, diagnostic loop questions).

---

## More from this author

See [allemaar/papers](https://github.com/allemaar/papers) for the full research program — current and forthcoming papers across Textual Kinematics (TK), Yon Notation (YON), Sightline Encoding Notation (SEN), Elastic Automators (EA), and Sai (SAI).

---

## License

Paper text and figures: [CC-BY-4.0](LICENSE). Any code in subdirectories: MIT, unless stated otherwise.
