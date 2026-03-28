***

# HyperSpaceX-D

**Deep Learning Project: Radial and Angular Exploration of HyperSpherical Dimensions**

This repository contains the code and replication experiments for the **HyperSpaceX-D** project.The project addresses the limitations of standard hyperspherical models (like ArcFace) that suffer from feature entanglement in densely populated spaces by exploring multi-hyperspherical spaces 

## Key Novelties

1. **Decoupled Radial-Angular Loss:** Resolves the gradient "tug-of-war" seen in the original DistArc loss when bottlenecked to 2D. By completely removing the radial penalty from the Softmax denominator, this loss optimizes angular and radial forces independently.
2. **Instance-Conditioned Dynamic Manifolds (ICDM):** Repurposes the radial dimension as an active axis of epistemic uncertainty.It dynamically sorts instances by semantic hardness (e.g., pushing occluded or noisy images to outer radial shells) without requiring external labels.

## Replication Results

The following table summarizes the replication results across different backbone architectures and embedding dimensions:

| Backbone | Embedding Dim | Loss / Method | Accuracy |
| :--- | :---: | :--- | :--- |
| **iResNet50** | 512D | Cross-Entropy | 61.77% |
| **iResNet50** | 512D | DistArc | 56.61% |
| **iResNet50** | 512D | Decoupled Loss | **64.95%** |
| **iResNet50** | 512D | ICDM | 51.00% |
| **ViT-B** | 512D | Cross-Entropy | 85.00% |
| **ViT-B** | 512D | DistArc | 77.96% |
| **ViT-B** | 512D | ICDM | **83.94%** |
| **ViT-B** | 2D | DistArc | ~72.00% |
| **ViT-B** | 2D | Cross-Entropy | - |

## Repository Structure

The repository consists of Jupyter Notebooks categorized by model backbone and applied loss function:

### ViT-B Experiments
* `ViT-B_512_crossentropy.ipynb` - Baseline Cross-Entropy runs at 512D.
* `ViT-B_512_distarc.ipynb` - Baseline DistArc runs at 512D.
* `ViT-B_512_ICDM.ipynb` - Novelty: Instance-Conditioned Dynamic Manifolds at 512D.
* `vitb-distarc-dim-2 (1).ipynb` - Baseline DistArc runs bottlenecked to 2D.
* `ViT-B_2_decoupled.ipynb` - Novelty: Decoupled Loss runs at 2D.

### iResNet50 Experiments
* `iResNet50_512_crossentropy.ipynb` - Baseline Cross-Entropy runs at 512D.
* `iResNet50_512_dist_arc.ipynb` - Baseline DistArc runs at 512D.
* `iResNet50_512_decoupled.ipynb` - Novelty: Decoupled Loss runs at 512D.
* `iresnet-novel.ipynb` - General novel architecture experiments for iResNet.

### Dataset Specific & Visualizations
* `DecoupledCIFAR10.ipynb` - Decoupled topology visualizations on CIFAR-10.
* `DecoupledMnist.ipynb` - Decoupled topology visualizations on MNIST.
* `cifar10-novel-ICDM.ipynb` - Dynamic Manifolds tested on CIFAR-10.
* `ICDM-mnist.ipynb` - Dynamic Manifolds tested on MNIST.
* `decoupled_simultaneous_radial_angular_conve...` - Convergence visualizations.
* `dynamic_distarc_animation.html` - HTML animation demonstrating the dynamic DistArc optimization.
* `outputimages/` - Contains the 2D latent space visualization plots.

## Team
* Tejas Kalkar
* Vishwaksen
* Vara Prasad
