# Image Augmentation Techniques Cheatsheet

| **Technique**        | **Description**                                                                                           | **Purpose**                                                                                     | **Applications**                                           |
|----------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|------------------------------------------------------------|
| **Horizontal Flip**   | Flips the image horizontally (mirror effect).                                                             | Increases dataset diversity and handles left-right symmetry.                                     | Object detection, face recognition                          |
| **Vertical Flip**     | Flips the image vertically.                                                                               | Not common for most cases, useful in special domains like satellite imagery.                     | Aerial/satellite images, microscopy                         |
| **Rotation**          | Rotates the image by a random degree (e.g., 0-360°).                                                      | Helps model to generalize across different orientations.                                         | Handwriting recognition, character detection                |
| **Random Crop**       | Crops a random section of the image and resizes it back to original size.                                 | Improves robustness to spatial transformations and localization.                                | Object localization, face detection                         |
| **Translation**       | Shifts the image in x and y directions.                                                                   | Simulates object translation and builds spatial invariance.                                      | Object detection                                            |
| **Scaling**           | Resizes the image either up or down.                                                                      | Simulates objects at different sizes in the real world.                                          | Object recognition, multi-scale detection                   |
| **Shear**             | Shears the image along x or y axis (slanting the image).                                                  | Encourages the model to handle slanted object views.                                             | Text recognition, character classification                  |
| **Zoom**              | Zooms into a section of the image.                                                                        | Simulates objects being closer or further in the image.                                          | Object recognition, face detection                          |
| **Brightness**        | Randomly adjusts the brightness level of the image.                                                       | Improves robustness to lighting variations.                                                      | Outdoor scenes, object tracking                             |
| **Contrast**          | Adjusts the contrast of the image, either increasing or decreasing it.                                    | Enhances the model's capability to work under different lighting conditions.                     | Outdoor scenes, medical imaging                             |
| **Saturation**        | Varies the saturation of the image.                                                                       | Helps models generalize in different lighting and scene conditions.                              | Outdoor imagery, product detection                          |
| **Hue**               | Shifts the hue channel of the image.                                                                      | Adds diversity in environments with varying color conditions.                                    | Image stylization, object detection in nature               |
| **Gaussian Noise**    | Adds random noise to the image.                                                                           | Makes the model robust to noisy environments.                                                    | Low-quality or noisy datasets (e.g., medical images)         |
| **Cutout**            | Randomly masks a square area of the image.                                                                | Encourages the model to focus on partial views of objects.                                       | Object recognition under occlusion                          |
| **Blur**              | Applies a blurring effect (Gaussian blur, motion blur).                                                   | Helps with handling unfocused or low-quality images.                                             | Motion detection, photography                               |
| **Sharpen**           | Increases the sharpness of the image.                                                                     | Improves clarity in edge detection and details.                                                  | Object detection in clear environments                      |
| **Elastic Deformation**| Warps the image in a non-linear way, distorting objects.                                                  | Improves robustness to non-linear deformations, common in real-world data.                       | Handwritten digit recognition, medical imaging              |
| **Grayscale Conversion** | Converts the image to grayscale.                                                                       | Reduces dependency on color information, focuses on texture or structure.                        | Medical imaging, surveillance                               |
| **Channel Shuffling** | Randomly shuffles the color channels (RGB).                                                               | Helps model learn color-invariant features.                                                      | General object recognition                                  |
| **Random Erasing**    | Randomly erases a portion of the image.                                                                   | Forces the model to learn from incomplete information, similar to cutout.                        | Robustness to occlusion in object detection                 |
| **Affine Transform**  | Applies a combination of translation, scaling, and shearing.                                              | Captures a variety of spatial transformations.                                                   | Object detection, image manipulation                        |
| **Perspective Transform** | Alters the perspective (3D warping effect).                                                           | Simulates viewing the image from different angles.                                               | Scene understanding, 3D object recognition                  |
| **Mixup**             | Combines two images with weighted pixel summation.                                                        | Creates augmented images by blending two samples, helping model learn object overlap.            | Object classification, segmentation                         |
| **CutMix**            | Combines two images by cutting out a section of one and pasting onto another.                             | Forces model to identify objects in occluded regions.                                            | Object classification, robust detection                     |

---

**Usage Notes:**

- **Mix and Match**: Most augmentation techniques can be combined to create even more diverse datasets.
- **Task-Specific**: Some techniques like `vertical flip`, `elastic deformation`, or `cutout` are more suited to certain domains like medical imaging, text recognition, or object occlusion.
- **Hyperparameter Tuning**: Parameters like the degree of rotation, the amount of zoom, or the noise level can be tuned to best match the dataset needs.
- **Data Augmentation Libraries**: Libraries such as `imgaug`, `Albumentations`, `Keras ImageDataGenerator`, and `torchvision.transforms` provide implementations for most of these techniques.