# CosmologicalEmulators

<img width="250" alt="CosmologicalEmulators logo" src="https://github.com/CosmologicalEmulators/.github/assets/58727599/e8f44547-113c-48a0-b69d-0d14957f82e2">

This Github organization puts together several codes, whose aim is to emulate cosmological observables as predicted by Einsten-Boltzmann solvers and Perturbation Theory codes. The main programming language employed in these repositories is `Julia`, but we also have pure `jax` ports of these packages.

Actually, the observables we emulates are:

- CMB angular Power Spectrum, with [`Capse.jl`](https://github.com/CosmologicalEmulators/Capse.jl) and [`jaxcapse`](https://github.com/CosmologicalEmulators/jaxcapse)
- Galaxy Clustering Power Spectrum multipoles based on EFT with [`Effort.jl`](https://github.com/CosmologicalEmulators/Effort.jl) and [`jaxeffort`](https://github.com/CosmologicalEmulators/jaxeffort)
- Linear and Nonlinear Matter Power Spectra with [`Mapse.jl`](https://github.com/CosmologicalEmulators/Mapse.jl) and [`jaxmapse`](https://github.com/CosmologicalEmulators/jaxmapse)
- BAO correlation function with [`Bora.jl`](https://github.com/CosmologicalEmulators/Bora.jl) and [`jaxbora`](https://github.com/CosmologicalEmulators/jaxbora)

We also provide a package, [`EmulatorsTrainer.jl`](https://github.com/CosmologicalEmulators/EmulatorsTrainer.jl), that has utilities to create training datasets, train emulators, and validate their performance.

Currently, we employ two different neural network backends for the `Julia` emulators:

- [`SimpleChains.jl`](https://github.com/PumasAI/SimpleChains.jl), a high-performance framework tailored for small NNs running on a CPU
- [`Lux.jl`](https://lux.csail.mit.edu/stable/), which is fully GPU compatible

Although the former is (in general) faster for our applications, the latter opens to the possibility of compiling the whole pipeline with [`Reactant.jl`](https://github.com/EnzymeAD/Reactant.jl), which gives for free compatibility with hardware accelerators (GPUs and TPUs) and high-performance differentiation with [`Enzyme.jl`](https://github.com/EnzymeAD/Enzyme.jl). For the `JAX` emulators, we employ [`flax`](https://github.com/google/flax) as the NN-backend.

Our emulators are differentiable, _i.e._ we can use automatic (also dubbed _algorithmic_) differentiation in order to evaluate derivatives. This enable for gradient-based methods, such as the minimization L-BFGS algorithm (as implemented in [`Optim.jl`](https://github.com/JuliaNLSolvers/Optim.jl)) or the Hamiltonian MonteCarlo inference algorithm (as implemented in [`Turing.jl`](https://github.com/TuringLang/Turing.jl)). The same is true for our `JAX`-based emulators, which we explicitely check can be differentiated end-to-end.

## Publications

Our codes have been officially released in the following publications:
- Bonici, Bianchini, and Ruiz-Zapatero, _Capse.jl: efficient and auto-differentiable CMB power spectra emulation_ [![arXiv](https://img.shields.io/badge/arXiv-2307.14339-b31b1b.svg)](https://arxiv.org/abs/2307.14339)
- Bonici, D'Amico, Bel, and Carbone, _Effort.jl:  a fast and differentiable emulator for the Effective Field Theory of the Large Scale Structure of the Universe_ [![arXiv](https://img.shields.io/badge/arXiv-2501.04639-b31b1b.svg)](https://arxiv.org/abs/2501.04639)

The codes previously listed are used in the following publications:
- Crespi, Percival, Krolewski, Bonici, et al., _Baryon fraction from the BAO amplitude: a consistent approach to parameterizing perturbation growth_ [![arXiv](https://img.shields.io/badge/arXiv-2511.23459-b31b1b.svg)](https://arxiv.org/abs/2511.23459)
- Krolewski, Crespi, Percival, Bonici, et al., _A measurement of H0 from DESI DR1 using energy densities_ [![arXiv](https://img.shields.io/badge/arXiv-2511.23432-b31b1b.svg)](https://arxiv.org/abs/2511.23432)
- Crespi, Bonici, Loureiro, et al., _Flinch: A Differentiable Framework for Field-Level Inference of Cosmological parameters from curved sky data_ [![arXiv](https://img.shields.io/badge/arXiv-2510.26691-b31b1b.svg)](https://arxiv.org/abs/2510.26691v1)
- Morawetz, Zhang, Bonici, Percival, Crespi, et al., _Frequentist Cosmological Constraints from Full-Shape Clustering Measurements in DESI DR1_ [![arXiv](https://img.shields.io/badge/arXiv-2508.11811-b31b1b.svg)](https://arxiv.org/abs/2508.11811)
- Zhang, Bonici, Rocher, Percival, de Mattia, et al., _Enhancing DESI DR1 Full-Shape analyses using HOD-informed priors_ [![arXiv](https://img.shields.io/badge/arXiv-2504.10407-b31b1b.svg)](https://arxiv.org/abs/2504.10407)
- Baleato Lizancos, Seljak, Karamanis, Bonici, Ferraro, _Selecting samples of galaxies with fewer Fingers-of-God_ [![arXiv](https://img.shields.io/badge/arXiv-2501.10587-b31b1b.svg)](https://arxiv.org/abs/2501.10587)
- Paradiso, Bonici, Chen, Percival, D'Amico, Zhang, and McGee, _Reducing nuisance prior sensitivity via non-linear reparameterization, with application to EFT analyses of large-scale structure_ [![arXiv](https://img.shields.io/badge/arXiv-2412.03503-b31b1b.svg)](https://arxiv.org/abs/2412.03503)
- SPT Collaboration, _Cosmology From CMB Lensing and Delensed EE Power Spectra Using 2019-2020 SPT-3G Polarization Data_ [![arXiv](https://img.shields.io/badge/arXiv-2411.06000-b31b1b.svg)](https://arxiv.org/abs/2411.06000)
- Zhang, Bonici, D'Amico, Paradiso, and Percival, _HOD-informed prior for EFT-based full-shape analyses of LSS_ [![arXiv](https://img.shields.io/badge/arXiv-2409.12937-b31b1b.svg)](https://arxiv.org/abs/2409.12937)
