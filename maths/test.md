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
\Phi^A = N^{-1} |\sum_{t=1}^{N}e^{i\phi^A_t}|
$$

Note that $\Phi^A$ is a complex vector whose length is not necessarily 1.


## Debiasing as demeaning

The debiasing procedure removes the mean resultant $\Phi^A$ from the unit-length vectors with $\phi^A$ as angles

$$
dPAC = N^{-1} |\sum_{t=1}^N [m^B_t (e^{i\phi^A_t}-\Phi^A)]|
$$

The debiasing procedure is in fact a **demeaning** of the unit-length complex-valued vectors with phase $\phi^A$

The demeaning procedure yields another complex-valued vector $\vec{d^A}$

$$
e^{i\phi^A_t}-\Phi^A=\vec{d_t^A} \ \ \ \ \ , \forall t
$$

Therefore we can re-express dPAC using the demeaned A's phase vector $d^A$. In these terms, dPAC is the mean resultant length of the complex-value vectors built as the scaling of the _demeaned_ phase of signal A by the magnitudes $m^B$ and.

$$
dPAC = N^{-1} |\sum_{t=1}^Nm_t^B \vec{d^A_t}|
$$

The "d" in dPAC is used for "debiased" but the mean resultant is a biased estimator anyway, so this terminology is a bit misleading. I rather consider the "d" as "demeaned" with the caveat that it's only the phase information that has been demeaned: demeaned-phase amplitude coupling (dPAC). 

## Normalized dPAC

Let's split the complex-valued vector $d^A$ into the magnitude and angle components and let's label them for sake of simplicity.

$$
|d^A| = n^A
$$

$$
\arg(d^A) = \theta^A
$$

$$
d^A = n^A e^{i \theta^A}
$$

Let's re-write dPAC once more.

$$
dPAC = N^{-1}|\sum_{t=1}^Nm^B_tn^A_te^{i\theta^A_t}|
$$

This formulation, differently from all other formulations of dPAC above clearly separates the magnitude information (i.e., $m_t^B$ and $n_t^A$) from the angle information (i.e., $\theta^A$). So, this makes it easier to see that, if we ever wanted dPAC to live in the [0, 1] range we need to scale it by the magnitude information. Here is normalized dPAC

$$
dPAC_n = \frac
{N^{-1}|\sum_{t=1}^N m^B_t n^A_t e^{i\theta^A_t}|}
{N^{-1}\sum_{t=1}^N m^B_t n^A_t}
$$