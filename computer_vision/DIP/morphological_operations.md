| **Operation**        | **Description**                                                                      | **Purpose**                                | **Applications**                                          |
|----------------------|--------------------------------------------------------------------------------------|--------------------------------------------|-----------------------------------------------------------|
| **Dilation**         | Expands the boundaries of objects in the image.                                      | Fills small holes, connects objects        | Object detection, binary segmentation                     |
| **Erosion**          | Shrinks the boundaries of objects in the image.                                      | Removes noise, disconnects objects         | Noise reduction, edge detection                           |
| **Opening**          | Erosion followed by dilation.                                                        | Removes small noise without affecting the object’s size | Noise removal in binary images                            |
| **Closing**          | Dilation followed by erosion.                                                        | Fills small gaps or holes in objects       | Hole filling, object reconstruction                       |
| **Morphological Gradient** | Difference between dilation and erosion.                                         | Highlights the edges of objects            | Edge detection, feature extraction                        |
| **Top-hat Transform** | Difference between input image and its opened version.                               | Extracts bright regions from a dark background | Background subtraction, feature extraction               |
| **Black-hat Transform** | Difference between input image and its closed version.                              | Extracts dark regions from a bright background | Contrast enhancement, feature extraction                  |