Here are the Markdown tables for super resolution, including both loss functions and metrics:

### Super Resolution Loss Functions

| Loss Function        | Purpose | Formula | Key Points |
|----------------------|---------|---------|------------|
| **Mean Squared Error (MSE)** | Measures the average squared difference between the predicted and true high-resolution images | **$\mathcal{L}_{\text{MSE}} = \frac{1}{N} \sum_{i=1}^{N} \left( \text{HR}_i - \hat{\text{HR}}_i \right)^2$** <br><br> *where:* <br> $\text{HR}_i$: True high-resolution pixel value <br> $\hat{\text{HR}}_i$: Predicted high-resolution pixel value | - **Pros:** Simple and effective for training <br> - **Cons:** Can produce overly smooth results; does not capture perceptual quality |
| **Mean Absolute Error (MAE)** | Measures the average absolute difference between the predicted and true high-resolution images | **$\mathcal{L}_{\text{MAE}} = \frac{1}{N} \sum_{i=1}^{N} \left\| \text{HR}_i - \hat{\text{HR}}_i \right\|$** <br><br> *where:* <br> $\text{HR}_i$: True high-resolution pixel value <br> $\hat{\text{HR}}_i$: Predicted high-resolution pixel value | - **Pros:** Less sensitive to outliers than MSE <br> - **Cons:** May not capture fine details effectively |
| **Perceptual Loss** | Measures the difference in high-level feature representations between the predicted and true images | **$\mathcal{L}_{\text{Perceptual}} = \frac{1}{N} \sum_{i=1}^{N} \left\| \phi(\text{HR}_i) - \phi(\hat{\text{HR}}_i) \right\|^2$** <br><br> *where:* <br> $\phi$: Feature extractor (e.g., VGG network) <br> $\text{HR}_i$: True high-resolution image <br> $\hat{\text{HR}}_i$: Predicted high-resolution image | - **Pros:** Captures perceptual quality and texture <br> - **Cons:** Computationally expensive; depends on feature extractor |
| **Adversarial Loss** | Uses a discriminator network to ensure that generated images appear realistic | **$\mathcal{L}_{\text{Adv}} = - \log D(\hat{\text{HR}})$** <br><br> *where:* <br> $D(\hat{\text{HR}})$: Probability that the discriminator considers the image as real | - **Pros:** Encourages more realistic image generation <br> - **Cons:** Requires a separate adversarial network; can be unstable |
| **Content Loss**     | Measures the difference between content features extracted from a pre-trained network | **$\mathcal{L}_{\text{Content}} = \frac{1}{N} \sum_{i=1}^{N} \left\| \text{Feature}_i - \hat{\text{Feature}}_i \right\|^2$** <br><br> *where:* <br> $\text{Feature}_i$: Feature map from true image <br> $\hat{\text{Feature}}_i$: Feature map from predicted image | - **Pros:** Focuses on preserving content details <br> - **Cons:** May not directly correlate with perceptual quality |

### Super Resolution Metrics

| Metric                | Purpose | Formula | Key Points |
|-----------------------|---------|---------|------------|
| **Peak Signal-to-Noise Ratio (PSNR)** | Measures the quality of the reconstructed image by comparing it to the original high-resolution image | **$\text{PSNR} = 10 \log_{10} \left(\frac{L^2}{\text{MSE}}\right)$** <br><br> *where:* <br> $L$: Maximum possible pixel value <br> $\text{MSE}$: Mean Squared Error between the original and reconstructed images | - **Pros:** Standard metric for image quality <br> - **Cons:** Does not always reflect perceptual quality |
| **Structural Similarity Index (SSIM)** | Measures the similarity between the original and reconstructed images by comparing luminance, contrast, and structure | **$\text{SSIM} = \frac{(2\mu_x \mu_y + C_1)(2\sigma_{xy} + C_2)}{(\mu_x^2 + \mu_y^2 + C_1)(\sigma_x^2 + \sigma_y^2 + C_2)}$** <br><br> *where:* <br> $\mu_x$, $\mu_y$: Mean of images x and y <br> $\sigma_x^2$, $\sigma_y^2$: Variances of images x and y <br> $\sigma_{xy}$: Covariance between images x and y <br> $C_1$, $C_2$: Small constants to avoid division by zero | - **Pros:** Reflects perceived image quality better than PSNR <br> - **Cons:** Computationally more complex |
| **Visual Information Fidelity (VIF)** | Measures the fidelity of the image by evaluating the amount of information retained in the reconstructed image | **$\text{VIF} = \sum_{i} \text{VIF}_i$** <br><br> *where:* <br> $\text{VIF}_i$: Visual information measure for each image region | - **Pros:** Reflects perceptual quality and visual information <br> - **Cons:** Computationally intensive |
| **Mean Absolute Error (MAE)** | Measures the average absolute difference between the predicted and true high-resolution images | **$\text{MAE} = \frac{1}{N} \sum_{i=1}^{N} \left\| \text{HR}_i - \hat{\text{HR}}_i \right\|$** <br><br> *where:* <br> $\text{HR}_i$: True high-resolution pixel value <br> $\hat{\text{HR}}_i$: Predicted high-resolution pixel value | - **Pros:** Simple to compute and interpret <br> - **Cons:** May not capture perceptual quality effectively |