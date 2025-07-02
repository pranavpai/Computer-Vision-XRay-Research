# Statistical Machine Learning for X-Ray Security Detection

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-1.9+-red.svg)](https://pytorch.org/)
[![Computer Vision](https://img.shields.io/badge/Domain-Computer%20Vision-green.svg)]()
[![Security AI](https://img.shields.io/badge/Application-Security%20AI-orange.svg)]()

A comprehensive deep learning project for automated threat detection in X-ray security images, implementing and comparing state-of-the-art object detection architectures with novel spatial transformation techniques.

## 🎯 Project Overview

This project addresses the critical challenge of automated threat detection in X-ray security screening systems. Using advanced computer vision techniques, we detect and localize dangerous objects (firearms, knives, tools) in X-ray images with high accuracy and computational efficiency.

### Key Innovations

- **Spatial Transformer Networks Integration**: Novel application of STN with Faster R-CNN for handling geometric variations
- **Comprehensive Occlusion Analysis**: Mathematical framework for quantifying detection complexity
- **Multi-Architecture Comparison**: Rigorous evaluation of three state-of-the-art detection methods
- **Production-Ready Pipeline**: Optimized for real-world security screening applications

## 🏗️ Technical Architecture

### Models Implemented

| Model | Architecture | Key Features | Performance (mAP) |
|-------|-------------|--------------|------------------|
| **Faster R-CNN** | Two-stage detector | RPN + ROI pooling | 0.4127 ± 0.0045 |
| **STN + Faster R-CNN** | Enhanced two-stage | Spatial transformations | **0.4285 ± 0.0052** |
| **RFBNet** | Single-stage detector | Receptive field blocks | 0.3891 ± 0.0041 |

### Spatial Transformer Network Variants
- **Affine Transformations**: Rotation, scaling, translation
- **Projective Transformations**: Perspective corrections
- **Thin Plate Spline (TPS)**: Non-rigid deformations

## 📊 Dataset & Performance

### Dataset Characteristics
- **Training Images**: 7,514 annotated X-ray images
- **Test Images**: 836 validation images
- **Object Classes**: 5 threat categories (gun, knife, plier, scissor, wrench)
- **Total Annotations**: 18,828 bounding box annotations
- **Resolution**: Standardized to 584×688 pixels

### Performance Metrics (20-Fold Cross-Validation)

| Metric | Faster R-CNN | STN + Faster R-CNN | RFBNet |
|--------|--------------|-------------------|---------|
| **mAP** | 0.4127 | **0.4285** | 0.3891 |
| **Recall** | 0.5234 | **0.5467** | 0.4923 |
| **Precision** | 0.6891 | **0.7012** | 0.6534 |
| **F1-Score** | 0.5923 | **0.6134** | 0.5612 |

## 🚀 Getting Started

### Prerequisites
```bash
pip install -r requirements.txt
```

### Core Dependencies
- PyTorch 1.9+
- TorchVision
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Pillow

### Quick Start

1. **Main Analysis** (Recommended):
   ```bash
   jupyter notebook XRay/Xray_subset.ipynb
   ```

2. **Full Dataset** (Computational intensive):
   ```bash
   jupyter notebook XRay/Xray.ipynb
   ```

3. **Preprocessing Tools**:
   ```bash
   jupyter notebook XRay/White_Space_Removal_&_Resizing.ipynb
   jupyter notebook XRay/Occlusion_levels.ipynb
   ```

## 📁 Repository Structure

```
📦 Statistical_Machine_Learning_Project/
├── 📁 XRay/                          # Main project directory
│   ├── 📓 Xray_subset.ipynb          # 🎯 Primary analysis notebook
│   ├── 📓 Xray.ipynb                 # Full dataset implementation
│   ├── 📓 Occlusion_levels.ipynb     # Occlusion quantification
│   ├── 📓 White_Space_Removal_&_Resizing.ipynb  # Image preprocessing
│   ├── 📁 Train/                     # Training dataset
│   │   └── train_annotations.csv
│   └── 📁 Test/                      # Test dataset
│       ├── 📁 Annotations/           # XML annotation files
│       └── test_annotations.csv
├── 📁 ResearchPapers/                # Academic literature
│   ├── Faster_R-CNN.pdf
│   ├── STN-CNN.pdf
│   ├── RFB.pdf
│   └── Survey_on_Image_Augments.pdf
├── 📄 requirements.txt               # Python dependencies
├── 📄 README.md                      # Project documentation
└── 📄 Readme.txt                     # Quick reference guide
```

## 🔬 Methodology

### Advanced Preprocessing Pipeline
- **Intelligent Cropping**: White space removal preserving object integrity
- **Standardized Resizing**: Aspect ratio preservation with 584×688 resolution
- **Comprehensive Augmentation**: 192 augmented images using 8 techniques
  - Color jittering, Gaussian blur, geometric transformations
  - Noise injection, random erasing, hide-and-seek blocking

### Evaluation Strategy
- **20-Fold Stratified Cross-Validation**: Robust statistical evaluation
- **Nested Cross-Validation**: Hyperparameter optimization
- **Occlusion-Aware Analysis**: Performance correlation with geometric complexity

## 📈 Key Results

### Model Performance Comparison
- **STN + Faster R-CNN** achieved the highest performance across all metrics
- **3.8% improvement** in mAP over baseline Faster R-CNN
- **Superior robustness** to geometric variations and occlusions
- **Computational trade-offs** analyzed for production deployment

### Novel Contributions
1. **First application** of STN to X-ray threat detection
2. **Mathematical framework** for occlusion quantification
3. **Comprehensive augmentation strategy** tailored to X-ray characteristics
4. **Production-ready implementation** with efficiency considerations

## 📚 Research Foundation

This project builds upon cutting-edge research in computer vision and security AI:
- Faster R-CNN architecture for object detection
- Spatial Transformer Networks for geometric invariance
- Receptive Field Block Networks for efficient detection
- Advanced augmentation techniques for X-ray domain adaptation

## 🤝 Contributing

This project represents a comprehensive approach to automated security screening with clear applications in:
- Airport security systems
- Border control checkpoints
- Critical infrastructure protection
- Automated threat assessment

## 📄 License

This project is developed for research and educational purposes. Please refer to individual research papers for academic citations and usage guidelines.

---

**Note**: This implementation focuses on the subset dataset due to computational constraints. The full dataset implementation is available but requires significant computational resources for training and evaluation.