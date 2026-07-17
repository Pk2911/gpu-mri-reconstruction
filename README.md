<<<<<<< HEAD
# gpu-mri-reconstruction
=======
# GPU-Accelerated Brain MRI Reconstruction

This project evaluates GPU-accelerated MRI reconstruction methods using PyTorch and CUDA. It simulates undersampled, noisy k-space data from brain MRI images, then compares four reconstruction approaches:


The notebook reports reconstruction quality with PSNR and SSIM, GPU memory use, batch time, and throughput, and produces a visual comparison.

## Repository layout

```text
notebooks/gpu_mri_reconstruction.ipynb  Main experiment notebook
docs/project-report.docx                 Full project report
docs/execution-notes.docx                Technical execution notes
docs/execution-of-code.pdf               Execution summary
requirements.txt                         Python dependencies
```

## Requirements


```text
Dataset/
  Training/
    tumor/
    no tumor/
  Testing/
    tumor/
    no tumor/
```

Install the Python packages:

```bash
pip install -r requirements.txt
```

For GPU acceleration, install the PyTorch build matching your CUDA version from the [official PyTorch installer](https://pytorch.org/get-started/locally/).

## Run the notebook

1. Open `notebooks/gpu_mri_reconstruction.ipynb` in Jupyter Lab or VS Code.
2. Update the four dataset paths in the **Data Loading & Preprocessing** cell to point to your local `Dataset` directory.
3. Select a CUDA-enabled Python kernel and run all cells.

The notebook falls back to CPU if CUDA is unavailable. Its timing and GPU-memory calls are written for CUDA, so a CUDA-capable NVIDIA system is the intended environment.

## Notes

This is a research/academic simulation of MRI reconstruction, not a clinical or diagnostic system. Do not use it for patient-care decisions.

## License

No license has been selected yet. Add one before publishing or reusing the code outside the project team.
>>>>>>> b818bf4 (Initial commit: GPU MRI reconstruction project)
