
This optimisation approach uses a Gaussian Process (GP) surrogate model combined with an Upper Confidence Bound (UCB) acquisition function. The model was implemented in Python using scikit-learn and applied over ten sequential optimisation rounds across eight black-box benchmark functions.

Use The approach is intended for low-data, expensive black-box optimisation problems where uncertainty-aware decision-making is critical. It is suitable for smooth or moderately noisy objective functions with continuous input spaces. The method should not be used for highly discontinuous functions, large-scale optimisation problems, or settings requiring real-time decisions under strict latency constraints.

During early rounds, the strategy prioritised exploration using space-filling sampling to establish an initial surrogate model. As more observations became available, the Gaussian Process provided calibrated uncertainty estimates, allowing the UCB acquisition function to balance exploitation of high-performing regions with exploration of uncertain areas. Over successive rounds, the strategy increasingly focused on refining promising regions while maintaining sufficient exploration to avoid premature convergence.

Performance was evaluated qualitatively by tracking the best observed function values across rounds for each of the eight benchmark functions. Quantitative metrics included cumulative regret trends and improvement over initial baseline values. Due to the small query budget, results emphasise optimisation efficiency rather than asymptotic convergence.

The approach assumes that the underlying objective functions are continuous and reasonably smooth, allowing them to be approximated by a Gaussian Process with a Matérn kernel. The primary limitation is scalability, as GP inference becomes computationally expensive as the dataset grows. Additionally, the optimisation outcome is sensitive to kernel choice and acquisition hyperparameters, which may affect performance across different function classes.

The decision-making process is transparent and reproducible, as all model components and acquisition rules are explicitly defined. This transparency supports interpretability, reproducibility, and adaptation to real-world optimisation tasks. The approach avoids opaque heuristics, enabling users to understand and audit why specific query points are selected.
