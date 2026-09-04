# Monte Carlo Project

This project performs a simple Monte Carlo estimate for a function over the interval $[-1, 1]$ and then generates simulated particle-event outputs based on the sampled cosine angles.

## Requirements

- Windows with MSVC toolchain (`cl.exe`)
- Git repository is optional, but the project is designed to run as a standalone C++ executable

## Build

From PowerShell in the project folder:

```powershell
cl /EHsc Final_Monte_Carlo_Code.cpp /Fe:Final_Monte_Carlo_Code.exe
```

## Run

```powershell
.\Final_Monte_Carlo_Code.exe
```

## What it does

- Computes a Monte Carlo estimate of the integral
- Estimates the maximum sampled value and error
- Uses a hit-or-miss method to generate accepted event angles
- Prints event vectors and kinematic quantities for each accepted event

## Notes

- The code uses a fixed center-of-mass energy `ECM = 80`.
- The generated output is intended for inspection and demonstration, not for production physics software.
- You can adjust the number of iterations and generated events in `main()`.

## Fusion extension

The same three-stage pipeline (integrate a differential cross section, sample it by hit-or-miss,
build final-state four-vectors) has been generalized to D-T and D-D nuclear fusion in
[`fusion/`](fusion/): reactivity ⟨σv⟩(T) from the Bosch-Hale cross sections, acceptance-rejection
sampling of reacting ion pairs, two-body kinematics with a Lorentz boost to the lab frame, and
Doppler-broadened neutron spectra validated against the Brysk width. 100,000 events per run.

![Fusion results](fusion/figures/fusion_mc_results.png)

See [`fusion/README.md`](fusion/README.md) for build instructions, physics, and validation.
