# Machine learning standards

- Choose split strategy according to objective; group correlated observations together.
- Fit preprocessing solely on training folds and evaluate on untouched held-out data.
- Use appropriate naïve/physical/linear baselines before deep learning.
- Optimize on validation data; reserve test data for final evaluation.
- Report metrics with units, uncertainty or distributions across cases where possible.
- Document target definition, leakage checks, deployment domain, and distribution shift.
