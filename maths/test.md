---
layout: page
title: test
---

# "debiased" phase-amplitude coupling (PAC)

## What is there to debias in PAC

Let's consider two signals, A and B. Of signal A we are only interested in its phase. Of signal B its magnitude. Let's assume we have a vector of multiple phases and magnitudes.

I will refer to the vector of phases from signal A as $\phi^A$ and to the vector of magnitudes from signal B as $m^B$.

PAC is the mean resultant length of the complex-valued vectors assembled as below.

$$
PAC = N^{-1} \sum_{t=1}^{N} ( m^B_t e^{i \phi^{A}_t})
$$

The bias $\Phi^A$ consists in a possible non-uniformity distribution of signal A's phases. This bias can be computed as the mean resultant of the unit-length complex vectors with angle $\phi^A$.

$$
\Phi^A = N^{-1} \sum_{t=1}^{N}e^{i\phi^A_t}
$$

Note that $\Phi^A$ is a complex vector whose length is not necessarily 1.

The debiasing procedure removes the mean resultant $\Phi^A$ from the unit-length vectors with $\phi^A$ as angles