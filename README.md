# Bayesian Optimisation for Black-Box Functions (BBO Capstone Project)

## Non-Technical Explanation

This project explores how Bayesian Optimisation can be used to make efficient decisions when evaluating a system is expensive and limited. Instead of trying every possible option, the method learns from previous results and intelligently suggests where to try next.

Using a Gaussian Process model and an uncertainty-aware strategy, the optimisation process balances exploration of new regions with refinement of promising ones. Across multiple iterations, the approach helps identify stable and reliable input regions rather than chasing constant performance jumps. The project demonstrates how thoughtful decision-making under uncertainty can be more valuable than aggressive optimisation when resources are constrained.

## Data

The data consists of sequential input–output pairs generated through weekly queries to a set of black-box functions provided by the Imperial College BBO platform. Each input represents a candidate solution, and each output is the corresponding scalar function evaluation.

The dataset was built incrementally over multiple optimisation rounds under a limited query budget. The uploaded `.npy` files represent the final snapshot of the dataset used in the optimisation process.

## Model

A Bayesian Optimisation framework was used, based on a Gaussian Process (GP) surrogate model with a Matérn 5/2 kernel. An Upper Confidence Bound (UCB) acquisition function guided the selection of new query points by balancing predicted performance and uncertainty.

This model was chosen for its interpretability, suitability for low-data regimes, and ability to explicitly manage uncertainty in black-box optimisation tasks.

## Hyperparameter Optimisation

The optimisation strategy focused on maintaining a stable and interpretable setup rather than aggressively tuning hyperparameters. Kernel choice and acquisition behaviour were selected based on standard Bayesian optimisation practices. As more data became available, the effective balance between exploration and exploitation shifted naturally without frequent manual intervention.

## Results

The optimisation results varied across functions. Some functions showed gradual improvement over time, while others exhibited stable or noisy behaviour under the given budget constraints. Rather than pursuing large performance jumps, the process emphasised consistency, confirmation of promising regions, and avoidance of regression.

These outcomes highlight the importance of uncertainty management and realistic expectations in black-box optimisation problems with limited evaluations.

## Repository Structure

- `BBO_Notebook-2.ipynb`: Main Jupyter Notebook demonstrating the optimisation workflow.
- `data/`: Input–output datasets used during optimisation.
- `datasheet.md`: Datasheet describing the dataset and its limitations.
- `modelcard.md`: Model card documenting the optimisation model and assumptions.
