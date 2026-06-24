# Formalizing and Falsifying Causal Pathways of Rare Events

This repository contains code to reproduce the Gaussian-example plots from the paper:


`Anahita Haghighat, Dominik Janzing (2026). Formalizing and Falsifying Causal Pathways of Rare Events. ICML 2026.`


## Examples

### Example 4.6

This example uses the bivariate Gaussian structural model

$$
X \sim \mathcal N(0,1),
\qquad
Y = \rho X + N_Y,
\qquad
N_Y \sim \mathcal N(0,1-\rho^2),
$$

where $X \perp N_Y$. This gives a standard Gaussian pair $(X,Y)$ with Pearson correlation $\rho$.

The script plots isolines of the explanation score

$$
1-
\frac{
\log P(Y\ge y\mid X\ge x)
}{
\log P(Y\ge y)
}.
$$

### Example 4.8

This example uses the structural model

$$
X \sim \mathcal N(0,1),\qquad
Y = \alpha X + N_Y,\qquad
Z = \beta X + \gamma Y + N_Z,
$$

where $X,N_Y,N_Z$ are mutually independent Gaussian variables. The noise variances are chosen so that $Y$ and $Z$ are standard Gaussian.

The default parameters are

$$
\alpha=-0.9,\qquad
\beta=0.9,\qquad
\gamma=0.9,\qquad
x=1.
$$

These parameters create a negatively confounded setting: $Y$ has a large positive structural effect on $Z$, but the observational association between $Y$ and $Z$ is weakened by the dependence between $X$ and $Y$.

The script generates the explanation-score and abstraction-accuracy figures comparing the bivariate pathway abstraction $B_2 \to B_3$ with the trivariate pathway abstraction on $(B_1, B_2, B_3)$.


## Files

- `figure_example_4_6.py`: reproduces the plot for Example 4.6.
- `figure_example_4_8.py`: reproduces the plot for Example 4.8.
- `requirements.txt`: lists the required Python packages.

## Installation

Install the required Python packages with:

```bash
pip install -r requirements.txt
```

## Reproducing the figures

Run:

```bash
python figure_example_4_6.py
python figure_example_4_8.py
```
