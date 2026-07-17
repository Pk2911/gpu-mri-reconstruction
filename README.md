# GPU-Accelerated Brain MRI Reconstruction

![Status](https://img.shields.io/badge/Status-Research%20Project-success)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![GPU](https://img.shields.io/badge/Acceleration-NVIDIA%20CUDA-76B900)

GPU-Accelerated Brain MRI Reconstruction is a research project that evaluates how NVIDIA CUDA acceleration can improve reconstruction of undersampled and noisy brain MRI data. The project compares four reconstruction methods and measures both image quality and GPU performance.

This project is an academic MRI simulation. It is not a clinical or diagnostic system and must not be used for patient-care decisions.

## Key Features

- MRI k-space simulation with FFT, undersampling, and additive noise.
- Four reconstruction methods: ZFR, CG, ISTA, and RLS.
- GPU acceleration using PyTorch tensors and CUDA.
- Quality metrics: PSNR and SSIM.
- Performance metrics: execution time, GPU memory usage, and throughput.
- Visual comparison of source and reconstructed outputs.

## Tech Stack

- Python
- PyTorch + CUDA
- OpenCV
- NumPy
- scikit-image
- Matplotlib
- Jupyter Notebook

## Project Structure

```text
gpu-mri-reconstruction/
|-- notebooks/
|   `-- gpu_mri_reconstruction.ipynb
|-- docs/
|   |-- project-report.docx
|   |-- execution-notes.docx
|   `-- execution-of-code.pdf
|-- requirements.txt
|-- .gitignore
`-- README.md
```

## Local Installation and Setup

1. Clone the repository:

```bash
git clone https://github.com/Pk2911/gpu-mri-reconstruction.git
cd gpu-mri-reconstruction
```

2. Create and activate a virtual environment:

```bash
python -m venv .venv
```

Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

For GPU execution, install a CUDA-compatible PyTorch build from the official PyTorch installation guide:
https://pytorch.org/get-started/locally/

## Dataset Setup

Update the four dataset paths in the notebook Data Loading and Preprocessing cell to match your local dataset location.

```text
Dataset/
|-- Training/
|   |-- tumor/
|   `-- no tumor/
`-- Testing/
    |-- tumor/
    `-- no tumor/
```

The dataset is excluded from this repository through .gitignore.

## Run the Project

```bash
jupyter lab
```

Then open notebooks/gpu_mri_reconstruction.ipynb, select a CUDA-enabled kernel, and run all cells.

Pipeline summary:

1. Load and preprocess brain MRI images.
2. Move image batches to GPU memory.
3. Simulate undersampled and noisy MRI k-space data.
4. Reconstruct with ZFR, CG, ISTA, and RLS.
5. Compare PSNR, SSIM, execution time, memory usage, and throughput.

## Reconstruction Methods

| Method | Purpose |
| :--- | :--- |
| ZFR | Baseline reconstruction with zero-filled missing k-space data. |
| CG | Iterative optimization for reconstruction. |
| ISTA | Iterative thresholding to balance structure and noise reduction. |
| RLS | Iterative regularized data-consistency update. |

## Future Improvements

- Make dataset paths configurable.
- Add CPU-safe performance metrics and automatic CUDA checks.
- Save benchmark results to CSV.
- Add comparative PSNR, SSIM, memory, and timing plots.
- Explore deep-learning-based MRI reconstruction models.

## Documentation

Supporting reports and execution notes are in the docs folder.

## License

No license has been selected yet. Add one before publishing or reusing the code outside the project team.

## Authors

Anjali K S and Pankaj Krishna
