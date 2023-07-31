# CosmologicalEmulators

<img width="250" alt="CosmologicalEmulators logo" src="https://github.com/CosmologicalEmulators/.github/assets/58727599/e8f44547-113c-48a0-b69d-0d14957f82e2">

This Github organization puts together several codes, whose aim is to emulate Cosmological observables as predicted by Einsten-Boltzmann solvers and Perturbation Theory.

Actually, the observables we are emulating are:
- CMB angular Power Spectrum, with [`Capse.jl`](https://github.com/CosmologicalEmulators/Capse.jl)
- BAO correlation function with [`Bora.jl`](https://github.com/CosmologicalEmulators/Bora.jl)
- Galaxy Clustering Power Spectrum multipoles based on EFT with [`Effort.jl`](https://github.com/CosmologicalEmulators/Effort.jl)

Our emulators are built using the Julia programming language, although most of them have a Python wrapper to enable usage in the pipelines commonly employed by the cosmological community.

The Neural Network package we employ is [`SimpleChains.jl`](https://github.com/PumasAI/SimpleChains.jl), a high-performance framework tailored for small NNs running on a CPU. We plan to add support to other frameworks such as [`Lux.jl`](https://lux.csail.mit.edu/stable/), in order to have GPU compatibles emulators.

Our emulators are differentiable, _i.e._ we can use automatic (also dubbed algorithmic) differentiation in order to evaluate gradients. This enable for gradient-based methods, such as the minimization L-BFGS algorithm (as implemented in [`Optim.jl`](https://github.com/JuliaNLSolvers/Optim.jl)) or the HamiltonianMonteCarlo inference algorithm (as implemented in [`Turing.jl`](https://github.com/TuringLang/Turing.jl)).


## Publications
The codes previously listed are used in the following publications:
- Bonici, Bianchini, and Ruiz-Zapatero, _Capse.jl: efficient and auto-differentiable CMB power spectra emulation_ [![arXiv](https://img.shields.io/badge/arXiv-2307.14339-b31b1b.svg)](https://arxiv.org/abs/2307.14339)
