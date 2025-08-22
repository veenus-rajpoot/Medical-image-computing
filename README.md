# Super-Resolution using GANs for Medical Imaging

## Overview
This project explores **super-resolution (SR) techniques for medical images** using **Generative Adversarial Networks (GANs)**.  
High-resolution details such as microvasculature and soft exudates are crucial for **early diagnosis** in retinal imaging. Traditional upscaling methods (e.g., bicubic interpolation) often blur fine structures, limiting diagnostic value.  

## Approach
- Implemented a **GAN-based super-resolution pipeline** inspired by *"Medical Image SR using Improved GAN"* (Bing et al., IEEE Access 2019).  
- Introduced **Improved Squeeze-and-Excitation (SE) blocks** with residual scaling to preserve and enhance feature channels instead of suppressing them.  
- Designed a **Fusion Loss** combining pixel-level (L1, MSE), perceptual (VGG), and adversarial (Relativistic GAN) losses to balance fidelity, realism, and perceptual quality.  
- Used a **simplified EDSR-GAN architecture**, removing batch normalization, adding global residuals, and embedding improved SE blocks.  

## Dataset
- **STARE Dataset**: 397 high-resolution retinal images  
  - Train: 377 images  
  - Test: 20 images  
- Low-resolution (LR) images were generated via bicubic downsampling with scaling factors of **4×, 8×, and 16×**.  

## Results
- **4× Upscaling**: PSNR ↑ 2.6 dB (42.65 vs 40.03), SSIM ↑ to 0.9567  
- **8× Upscaling**: PSNR ↑ 4.5 dB (39.88 vs 35.41), SSIM ↑ to 0.9330  
- **16× Upscaling**: PSNR ↑ 5.0 dB (36.62 vs 31.60), SSIM ↑ to 0.9181  
- Generated images preserved **sharper edges** and **finer retinal details** compared to bicubic interpolation.  

## Key Contributions
- Demonstrated that **Improved SE blocks** maintain vital anatomical structures by preventing feature suppression in deep networks.  
- Showed that **Fusion Loss** effectively prevents over-smoothing while reducing hallucinated artifacts.  
- Achieved **state-of-the-art quality improvements** for medical image super-resolution on retinal datasets.  

## Future Scope
- Extend approach to **larger and diverse medical datasets** (CT, MRI).  
- Explore **3D medical image super-resolution** for volumetric scans.  
