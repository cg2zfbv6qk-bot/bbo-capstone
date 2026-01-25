# Datasheet for the BBO Capstone Dataset

## Motivation

The dataset was created to support a black-box optimisation task under a limited evaluation budget. The goal was not to train a predictive model for deployment, but to study decision-making under uncertainty using Bayesian optimisation techniques.

## Composition

The dataset consists of sequential input–output pairs:
- Inputs are continuous-valued vectors in the range [0, 1].
- Outputs are scalar function evaluations returned by black-box systems.

Each function has its own dataset, accumulated incrementally over multiple optimisation rounds.

## Collection Process

Data was generated through weekly interaction with the Imperial College BBO platform. At each iteration, a new input was proposed by the optimisation algorithm and evaluated externally. The returned output was then appended to the existing dataset.

## Preprocessing

No extensive preprocessing was applied. Inputs are used in their raw [0, 1] scale, and outputs are stored as returned by the black-box functions. This preserves transparency and avoids introducing additional assumptions.

## Intended Use

The dataset is intended solely for:
- Studying sequential decision-making in black-box optimisation.
- Demonstrating Bayesian optimisation workflows.

It is not intended for supervised learning benchmarks or general-purpose prediction tasks.

## Limitations

- The dataset is small due to strict query budget constraints.
- Outputs may be noisy or exhibit limited variation.
- There is no guarantee that the observed data covers the global optimum of any function.

## Ethical Considerations

The dataset contains no personal, sensitive, or identifiable information.
