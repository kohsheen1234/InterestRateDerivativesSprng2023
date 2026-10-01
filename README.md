# Interest Rate Derivatives: Vasicek & CIR Models

This repository contains quantitative analysis of **interest-rate dynamics and fixed-income derivatives**, with a primary focus on the **Vasicek** and **Cox-Ingersoll-Ross (CIR)** short-rate models.

The work applies stochastic processes, probability theory, and financial mathematics to model the evolution of interest rates and analyze interest-rate-sensitive financial instruments.

## Vasicek Model

The Vasicek model represents the short-term interest rate as a mean-reverting stochastic process:

$$
dr_t = \kappa(\theta - r_t)\,dt + \sigma\,dW_t
$$

where:

- $r_t$ is the short-term interest rate
- $\kappa$ is the speed of mean reversion
- $\theta$ is the long-run equilibrium interest rate
- $\sigma$ is the volatility parameter
- $W_t$ is a Wiener process

The drift term

$$
\kappa(\theta-r_t)
$$

pulls the interest rate toward its long-run mean $\theta$.

The Vasicek model captures the tendency of interest rates to return toward an equilibrium level over time. Future short rates are normally distributed, although the model can produce negative interest rates because volatility is constant.

## Cox-Ingersoll-Ross Model

The Cox-Ingersoll-Ross model extends the mean-reverting framework by making volatility dependent on the current interest-rate level:

$$
dr_t = \kappa(\theta-r_t)\,dt + \sigma\sqrt{r_t}\,dW_t
$$

The diffusion term

$$
\sigma\sqrt{r_t}
$$

causes volatility to decrease as the interest rate approaches zero.

A key property of the model is the **Feller condition**:

$$
2\kappa\theta \geq \sigma^2
$$

When this condition is satisfied, the short-rate process remains strictly positive.

## Vasicek vs. CIR

**Vasicek**

- Mean reverting
- Constant volatility
- Normally distributed future rates
- Can generate negative rates
- Supports analytical zero-coupon bond pricing

**CIR**

- Mean reverting
- Volatility depends on the current rate
- Transition distribution is related to the noncentral chi-square distribution
- Can preserve positive interest rates under the Feller condition
- Supports analytical zero-coupon bond pricing

The comparison shows how changing the diffusion process can significantly affect the statistical behavior of modeled interest rates.

## Fixed-Income Valuation

Both Vasicek and CIR are **short-rate models**, where the instantaneous interest rate $r_t$ drives the evolution of the term structure.

The price of a zero-coupon bond maturing at time $T$ can be expressed under the risk-neutral measure as

$$
P(t,T)
=
\mathbb{E}^{\mathbb{Q}}
\left[
\exp\left(
-\int_t^T r_s\,ds
\right)
\middle|
\mathcal{F}_t
\right].
$$

Here:

- $P(t,T)$ is the bond price at time $t$
- $T$ is the maturity date
- $r_s$ is the short-rate process
- $\mathbb{Q}$ is the risk-neutral probability measure
- $\mathcal{F}_t$ represents the information available at time $t$

For affine short-rate models such as Vasicek and CIR, zero-coupon bond prices can be written in the form

$$
P(t,T)
=
A(t,T)e^{-B(t,T)r_t}.
$$

The functions $A(t,T)$ and $B(t,T)$ depend on the parameters of the underlying short-rate model.

This affine structure allows interest-rate dynamics to be connected directly to the valuation of fixed-income securities.

## Technical Focus

The project explores:

- Stochastic differential equations
- Mean-reverting interest-rate processes
- Vasicek short-rate modeling
- Cox-Ingersoll-Ross short-rate modeling
- Conditional probability distributions
- Interest-rate volatility
- Long-run equilibrium behavior
- Risk-neutral valuation
- Zero-coupon bond pricing
- Term-structure modeling
- Fixed-income and interest-rate derivative analysis

## Repository Contents

The repository contains a sequence of reports covering mathematical and quantitative applications in interest-rate derivatives:

```text
IRD1_ShwetaPandey_KohsheenTiku_230203.pdf
IRD2_ShwetaPandey_KohsheenTiku_230210.pdf
IRD3_ShwetaPandey_KohsheenTiku_PrateekKumar_230224.pdf
IRD4_ShwetaPandey_KohsheenTiku_PrateekKumar_230310.pdf
IRDFKohsheenTiku230327.pdf
```

## Key Takeaway

This work applies **Vasicek and Cox-Ingersoll-Ross stochastic short-rate models** to analyze interest-rate behavior and fixed-income instruments.

The project connects stochastic differential equations, mean reversion, probability distributions, and risk-neutral valuation to understand how mathematical assumptions about interest-rate dynamics affect financial instrument pricing.
