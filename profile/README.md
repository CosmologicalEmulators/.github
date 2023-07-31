# CosmologicalEmulators

<img width="250" alt="CosmologicalEmulators logo" src="https://github.com/CosmologicalEmulators/Bora.jl/assets/58727599/aa69a7a0-52a0-498d-ad6f-aa15bfa39b82">

This organizations puts together several codes, whose aim is to emulate Cosmological observables as predicted by Einste-Boltzmann solvers and Perturbation Theory.

Actually, the observables we are emulating are:
- CMB angular Power Spectrum, with [`Capse.jl`](https://github.com/CosmologicalEmulators/Capse.jl)
- BAO correlation function with [`Bora.jl`](https://github.com/CosmologicalEmulators/Bora.jl)
- Galaxy Clustering Power Spectrum multipoles based on EFT with [`Effort.jl`](https://github.com/CosmologicalEmulators/Effort.jl)

These codes are based on a lower level package, `AbstractEmulator.jl`, where the common methods are defined.


## Publications
The codes previously listed are used in the following publications:
- Bonici, Bianchini, and Ruiz-Zapatero, Capse.jl: efficient and auto-differentiable CMB power spectra emulation [![arXiv](https://img.shields.io/badge/arXiv-2307.14339-b31b1b.svg)](https://arxiv.org/abs/2307.14339)
