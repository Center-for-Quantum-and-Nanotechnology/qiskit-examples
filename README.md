# qiskit-examples

Example notebooks using Qiskit and PySCF for quantum chemistry simulations.
The three notebooks form a deliberate progression in how much is built by
hand versus handed off to a library:

- `H2_VQE_example.ipynb` — H2 ground state via the Variational Quantum
  Eigensolver (VQE). Everything is built from scratch -- integrals, the
  Jordan-Wigner qubit Hamiltonian, the UCCSD circuit, the optimization loop
  -- with no `qiskit-nature` or `qiskit-addon-sqd`, purely to show what
  those packages actually do under the hood.
- `H2_SQD_example.ipynb` — H2 via Sample-based Quantum Diagonalization
  (SQD). Uses `qiskit-nature` for the Hamiltonian and UCCSD ansatz, but the
  SQD classical engine itself (determinant projection, configuration
  recovery, the iterate-and-diagonalize loop) is still hand-built, since at
  H2's small scale that engine is still the interesting part to see.
- `N2_SQD_example.ipynb` — N2 via SQD, at a scale where hand-building stops
  being illuminating and starts being impractical: `qiskit-nature` builds
  the Hamiltonian and ansatz, and the real `qiskit-addon-sqd` package runs
  the classical SQD engine. Also includes real IBM hardware execution and
  `SamplerV2`-based error mitigation.

## Setup

### Windows

PySCF doesn't install cleanly with pip on Windows, so use conda:

```
conda create -n pyscf_env python=3.13
conda activate pyscf_env
conda install -c conda-forge pyscf
pip install qiskit qiskit-aer qiskit-ibm-runtime qiskit[visualization] matplotlib jupyterlab
pip install qiskit-nature
pip install qiskit-addon-sqd
pip install qiskit-algorithms
```

### Linux / macOS

PySCF installs fine via pip, so the setup is simpler:

```
python -m venv pyscf_env
source pyscf_env/bin/activate
pip install pyscf qiskit qiskit-aer qiskit-ibm-runtime qiskit[visualization] matplotlib jupyterlab
pip install qiskit-nature
pip install qiskit-addon-sqd
pip install qiskit-algorithms
```

### Running the notebooks

You can run the notebooks with JupyterLab:

```
jupyter lab
```

Or open them directly in VS Code (with the Jupyter extension installed) and select the `pyscf_env` conda environment as the kernel.
