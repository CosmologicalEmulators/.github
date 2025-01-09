# CosmologicalEmulators

<img width="250" alt="CosmologicalEmulators logo" src="https://github.com/CosmologicalEmulators/.github/assets/58727599/e8f44547-113c-48a0-b69d-0d14957f82e2">

This Github organization puts together several codes, whose aim is to emulate cosmological observables as predicted by Einsten-Boltzmann solvers and Perturbation Theory codes.

Actually, the observables we emulates are:

- CMB angular Power Spectrum, with [`Capse.jl`](https://github.com/CosmologicalEmulators/Capse.jl)
- BAO correlation function with [`Bora.jl`](https://github.com/CosmologicalEmulators/Bora.jl)
- Galaxy Clustering Power Spectrum multipoles based on EFT with [`Effort.jl`](https://github.com/CosmologicalEmulators/Effort.jl)

Our emulators are built using the Julia programming language, although most of them have a Python wrapper to enable usage in the pipelines commonly employed by the cosmological community. Furthermore, we are currently working on pure Jax translations for some of our emulators.

Currently, we employ two different neural network backends for the Julia emulators:

- [`SimpleChains.jl`](https://github.com/PumasAI/SimpleChains.jl), a high-performance framework tailored for small NNs running on a CPU
- [`Lux.jl`](https://lux.csail.mit.edu/stable/), which is fully GPU compatible

Although the former is (in general) faster for our applications, the latter opens to the possibility of using samplers, such as [MicroCanonical Hamiltonian MonteCarlo](https://github.com/JaimeRZP/MicroCanonicalHMC.jl), that can easily run on a GPU.


Our emulators are differentiable, _i.e._ we can use automatic (also dubbed _algorithmic_) differentiation in order to evaluate derivatives. This enable for gradient-based methods, such as the minimization L-BFGS algorithm (as implemented in [`Optim.jl`](https://github.com/JuliaNLSolvers/Optim.jl)) or the Hamiltonian MonteCarlo inference algorithm (as implemented in [`Turing.jl`](https://github.com/TuringLang/Turing.jl)).


## Publications

Our codes have been officially released in the following publications:
- Bonici, Bianchini, and Ruiz-Zapatero, _Capse.jl: efficient and auto-differentiable CMB power spectra emulation_ [![arXiv](https://img.shields.io/badge/arXiv-2307.14339-b31b1b.svg)](https://arxiv.org/abs/2307.14339)
- Bonici, D'Amico, Bel Carbone, _Effort.jl:  a fast and differentiable emulator for the Effective Field Theory of the Large Scale Structure of the Universe_ [![arXiv](https://img.shields.io/badge/arXiv-2501.04639-b31b1b.svg)](https://arxiv.org/abs/2501.04639)

The codes previously listed are used in the following publications:
- Paradiso, Bonici, Chen, Percival, D'Amico, Zhang, McGee, _Reducing nuisance prior sensitivity via non-linear reparameterization, with application to EFT analyses of large-scale structure_ [![arXiv](https://img.shields.io/badge/arXiv-2412.03503-b31b1b.svg)](https://arxiv.org/abs/2412.03503)
- SPT Collaboration, _Cosmology From CMB Lensing and Delensed EE Power Spectra Using 2019-2020 SPT-3G Polarization Data_ [![arXiv](https://img.shields.io/badge/arXiv-2307.14339-b31b1b.svg)](https://arxiv.org/abs/2307.14339)
- Zhang, Bonici, D'Amico, Paradiso, Percival, _HOD-informed prior for EFT-based full-shape analyses of LSS_ [![arXiv](https://img.shields.io/badge/arXiv-2409.12937-b31b1b.svg)](https://arxiv.org/abs/2409.12937)
