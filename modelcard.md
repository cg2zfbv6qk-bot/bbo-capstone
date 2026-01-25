# Model Card: Bayesian Optimisation with Gaussian Processes

## Model Overview

This project uses a Bayesian Optimisation framework built around a Gaussian Process (GP) surrogate model and an Upper Confidence Bound (UCB) acquisition function.

## Intended Use

The model is intended for black-box optimisation problems where:
- Function evaluations are expensive or limited.
- The objective function is unknown.
- Decisions must be made sequentially under uncertainty.

## Model Details

- Surrogate Model: Gaussian Process Regression
- Kernel: Matérn 5/2
- Acquisition Function: Upper Confidence Bound (UCB)

The GP provides both mean predictions and uncertainty estimates, which are used by the acquisition function to guide query selection.

## Training Data

The model is trained iteratively on sequentially collected input–output pairs. The dataset grows over time as new evaluations are appended.

## Performance Characteristics

Performance is assessed qualitatively through:
- Stability of suggested inputs over iterations.
- Trends in best-so-far observed outputs.
- Reduction of unnecessary exploration as uncertainty decreases.

Due to the limited dataset size, quantitative performance metrics are not emphasised.

## Limitations

- The model does not guarantee convergence to a global optimum.
- Results depend heavily on the available query budget.
- Some functions may exhibit flat or noisy landscapes that limit observable improvement.

## Risks and Mitigations

Aggressive exploitation may lead to premature convergence. This risk is mitigated by using uncertainty-aware acquisition and maintaining exploratory behaviour when confidence is low.

## Ethical Considerations

The model operates on synthetic black-box functions and poses no ethical or societal risks.
