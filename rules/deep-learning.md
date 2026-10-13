# Deep learning standards

- Use deterministic seeds as feasible; document sources of GPU nondeterminism.
- Check device placement, CUDA version, package compatibility and memory before training.
- Implement stable batching, early stopping, gradient monitoring, and checkpoints.
- Keep configuration, model weights and dataset split IDs traceable.
- Compare against simpler baselines; inspect train/validation learning curves.
- Evaluate on independently held-out cases and report runtime and hardware.
