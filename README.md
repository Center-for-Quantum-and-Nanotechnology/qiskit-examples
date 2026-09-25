# qiskit-examples

Example notebooks using Qiskit and PySCF for quantum chemistry simulations:

- `H2_VQE_example.ipynb` — H2 ground state via the Variational Quantum Eigensolver (VQE)
- `H2_SQD_example.ipynb` — H2 via Sample-based Quantum Diagonalization (SQD) *(upcoming)*
- `N2_SQD_example.ipynb` — N2 via Sample-based Quantum Diagonalization (SQD) *(upcoming)*

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
