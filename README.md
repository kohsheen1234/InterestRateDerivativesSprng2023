# Interest Rate Derivatives: Vasicek & CIR Models

This repository contains quantitative analysis of **interest-rate dynamics and fixed-income derivatives**, with a primary focus on the **Vasicek** and **Cox-Ingersoll-Ross (CIR)** short-rate models.

The work applies stochastic processes, probability theory, and financial mathematics to model the evolution of interest rates and analyze the behavior and valuation of interest-rate-sensitive financial instruments.

## Vasicek Model

The Vasicek model describes the short-term interest rate using the mean-reverting stochastic differential equation

\[
dr_t = \kappa(\theta-r_t)dt+\sigma dW_t
\]

where:

- \(r_t\) is the short-term interest rate
- \(\kappa\) controls the speed of mean reversion
- \(\theta\) is the long-run equilibrium interest rate
- \(\sigma\) represents interest-rate volatility
- \(W_t\) is a Wiener process

The model captures the tendency of interest rates to move back toward a long-run level rather than evolve as an unconstrained random walk.

Analysis includes the probabilistic behavior of future short rates and the use of the model's affine structure for fixed-income valuation.

## Cox-Ingersoll-Ross Model

The CIR model extends the mean-reverting framework by making volatility dependent on the current interest-rate level:

\[
dr_t = \kappa(\theta-r_t)dt+\sigma\sqrt{r_t}\,dW_t
\]

The \(\sqrt{r_t}\) diffusion term changes the distributional behavior of the process and reduces volatility as rates approach zero.

Under the **Feller condition**

\[
2\kappa\theta \geq \sigma^2,
\]

the short-rate process remains strictly positive.

This makes CIR particularly useful for studying interest-rate dynamics where the behavior near zero is important.

## Vasicek vs. CIR

| Property | Vasicek | CIR |
|---|---|---|
| Mean reversion | Yes | Yes |
| Volatility | Constant | Rate-dependent |
| Rate distribution | Gaussian | Noncentral chi-square |
| Negative rates possible | Yes | Typically avoided under the Feller condition |
| Analytical bond pricing | Yes | Yes |

Studying both models highlights how assumptions about **drift, diffusion, mean reversion, and rate-dependent volatility** affect the probability distribution of future interest rates and the resulting valuation of fixed-income securities.

## Technical Focus

The project explores:

- Stochastic differential equations for short-rate dynamics
- Mean-reverting interest-rate processes
- Conditional expectations and probability distributions
- Vasicek and CIR model parameters
- Interest-rate volatility and long-run equilibrium behavior
- Zero-coupon bond valuation
- Term-structure and fixed-income analysis
- Probabilistic valuation of interest-rate-sensitive instruments
- Mathematical comparison of alternative short-rate assumptions

The central objective is to connect the mathematical structure of stochastic interest-rate models to their practical implications for **fixed-income pricing and financial risk analysis**.

## Repository Contents

The repository contains a sequence of reports covering problems and applications in interest-rate derivatives:

```text
IRD1_ShwetaPandey_KohsheenTiku_230203.pdf
IRD2_ShwetaPandey_KohsheenTiku_230210.pdf
IRD3_ShwetaPandey_KohsheenTiku_PrateekKumar_230224.pdf
IRD4_ShwetaPandey_KohsheenTiku_PrateekKumar_230310.pdf
IRDFKohsheenTiku230327.pdf
```
