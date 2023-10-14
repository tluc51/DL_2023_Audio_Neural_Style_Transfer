# Session Summary

This file indicates to summarize the work in each project session.

## Session 1

### Date

06 October 2023.

### Duration

1h15m.

### Session's goal

Read and understand the provided [paper](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf).

### Work summary

#### Work progress

4 (of 10) pages.

#### Paper summary

**Objective**: generate new high-quality images that combine the content of any given photograph with artistic or stylistic elements.

**Main contribution**:

- Extract texture of the target image using high-level image features (to overcome the limitation of previous methods in which only low-level ones are used).

**Method**:

- Independent manipulation of image content and style.
- ***Model structure***: A normalized version of 16 convolutional and 5 pooling layers of the VGG19 network and no usage of fully connected layers. The normalization is achieved by re-scaling the mean activation of each convolutional filter over images and positions to 1.
- ***Content representation***:
    - Pass the content image through the CNN to extract its content features. This typically involves selecting one or more intermediate layers in the network to capture the content.
    - The collection of feature maps of $l-th$ layer is represented as matrix $F^l \in \mathcal{R}^{N_{l} \times M_{l}}$, where $N_l$ is number of filters and $M_l$ is size of flatterned feature map.

- ***Style reperesentaion***:
    - Pass the style image through the CNN to extract its style features. These features are obtained by calculating the correlations between feature maps at different layers.
    - The Gram matrix $G$ represents the feature correlations in a certain layer and contains the correlations between different filter responses.

- ***Loss functions***:
    - The content loss is the mean squared error between the feature representations of the generated image and the content image.
    - The style loss measures the difference in the Gram matrices (a statistical measure of feature correlations) between the generated image and the style image at multiple layers.
    - The total loss is sum of the two losses with proper coefficients.

**Remark**: The generated image can be initialized as a white-noise image.

#### Encountered problem

- Why average pooling process performs better result ?
- Appropriate weighting factors to create a total loss function.

#### Next session

Continue and finish understanding the article.

## Session 2

### Date

13 October 2023.

### Duration

2h30m.

### Session's goal

Finish reading and understanding the paper, make a short presentation on the topic to other students and peer evaluation.

### Work summary

#### Work progress

Paper: completed.

#### Encountered problem

- No specified problems.

#### Next session

- Study the coding tutorial and try to implement the first steps.
- Collect data and perform data preprocessing.
