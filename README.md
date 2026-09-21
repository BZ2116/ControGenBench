# ControGenBench

ControGenBench is a benchmark for evaluating controversy-aware and risk-sensitive text generation. Unlike traditional safety benchmarks that treat all controversial content as harmful, ControGenBench distinguishes between **constructive disagreement** that enriches public discourse and **harmful content** that warrants intervention.

## Overview

ControGenBench evaluates whether language models can:

1. **Identify controversial claims** and assess their potential for constructive disagreement
2. **Select appropriate interventions** — from preserving valuable controversy to rewriting harmful content
3. **Perform localized revisions** that reduce risk while preserving author stance, semantic meaning, and discussion potential
4. **Calibrate automatic metrics** against human judgments across multiple evaluation dimensions

The benchmark operates at the **claim level**, focusing on individual debatable assertions within longer texts, rather than evaluating entire documents holistically.

## Tasks

| Task | Description | Metrics |
|------|-------------|---------|
| Claim Property Prediction | Predict disagreement potential, constructive disagreement potential, harmfulness, evidence risk, and author stance | Per-annotator agreement, distribution matching |
| Risk-Aware Action Selection | Choose among preserve, verify-first, qualify, incorporate counterarguments, de-escalate, rewrite, or refuse | Action agreement, constraint compliance |
| Constructive Disagreement Preservation | Localized revision that reduces risk without over-neutralizing | Human evaluation: risk, disagreement, constructiveness, stance, semantics, locality, quality |
| Metric Calibration | Evaluate whether automatic scores reflect human judgments across systems | Correlation, ranking consistency |

## Dataset Statistics

| Split | Cases | Claims | Revisions |
|-------|-------|--------|-----------|
| Train | _TODO_ | _TODO_ | _TODO_ |
| Dev | _TODO_ | _TODO_ | _TODO_ |
| Test | _TODO_ | _TODO_ | _TODO_ |
| **Total** | _TODO_ | _TODO_ | _TODO_ |

**Domains**: AI, Education, Entertainment

**Claim-level annotations per instance**: ≥3 human annotators

## Data Format

```
controgenbench/
├── cases/           # Source texts with context
│   ├── AI-0001.json
│   └── ...
├── claims/          # Extracted claims with spans
│   ├── AI-0001.json
│   └── ...
├── annotations/     # Human annotations
│   ├── properties/  # Claim property labels
│   ├── actions/     # Action selection
│   └── revisions/   # Revision evaluations
├── evaluations/     # System outputs and metrics
└── metadata/        # Source info, annotator demographics
```

Each claim includes:
- `text_span`: Character offsets identifying the claim in source text
- `properties`: Five core attributes (disagreement, constructiveness, harmfulness, evidence_risk, stance)
- `actions`: Recommended intervention with constraints
- `revisions`: Localized edits with human evaluation scores

## Evaluation

### Automatic Metrics

- Claim property prediction: Label distribution divergence, per-attribute accuracy
- Action selection: Exact match, constraint satisfaction rate
- Revision quality: COMET-based semantic similarity, edit distance, human alignment

### Human Evaluation

Systems are evaluated on:
1. **Risk reduction**: Does revision lower potential for harm?
2. **Disagreement preservation**: Does revision maintain valuable controversy?
3. **Constructiveness**: Does revised text invite productive discussion?
4. **Stance preservation**: Is author's position faithfully represented?
5. **Semantic fidelity**: Core meaning preserved?
6. **Locality**: Minimal unnecessary changes?
7. **Overall quality**: Fluency and naturalness of output?

## Download

_Before public release, all data will be available at:_

```
https://github.com/[org]/ControGenBench/releases
```

## Baseline Results

_System performance comparisons will be added after benchmark completion._

| System | Claim Prop. | Action Sel. | Rev. Quality | Metric Align. |
|--------|-------------|-------------|--------------|---------------|
| _TODO_ | _TODO_ | _TODO_ | _TODO_ | _TODO_ |

## Citation

```bibtex
@inproceedings{controgenbench2026,
  title={ControGenBench: A Benchmark for Controversy-Aware and Risk-Sensitive Multi-Agent Generation},
  author={},
  booktitle={Proceedings of the Conference on X},
  year={2026}
}
```

## License

The dataset is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Source texts are used under fair use for research purposes.

## Contact

For questions or issues, please open a GitHub issue or contact [TODO].
