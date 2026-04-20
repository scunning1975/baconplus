# baconplus

An R package (in development) that computes difference-in-differences
decomposition weights:

1. The binary **Goodman-Bacon (2021)** decomposition for TWFE under
   staggered timing.
2. The continuous-treatment TWFE decomposition from
   **Callaway, Goodman-Bacon and Sant'Anna ("CBS") v4 (2025)**, Table 1.

## Weights explorer

A standalone, browser-based tool for the CBS level weights lives at:

**https://scunning1975.github.io/baconplus/**

Pick a dose `l` and a kernel bandwidth. The app shows the six ingredients,
plugs them into

    w_lev(l) = (l - E[D]) * f_D(l) / Var(D)

and plots the full weight curve alongside the dose distribution. The
scaled-level, causal-response, and scaled 2x2 tabs are placeholders —
those decompositions will light up in future updates.

The default dose distribution is a simulated Lu & Yu (2015)-style setup:
155 Chinese industries, roughly 30% at `D = 0`, right-skewed positive
doses up to 0.60. The benchmark hand calculation from the companion
teaching deck reproduces inside the app:
`w_lev(0.10) = -6.65` at `bw = 0.025`.

## Status

Early scaffolding. The R functions themselves haven't landed yet — this
repo currently hosts the explorer while the package is being built.
