# Real-Time Object Tracking using Gaussian Mixture Models (GMM)

This repository contains the implementation of a Real-Time Object Tracking system using Gaussian Mixture Models (GMM). The project focuses on the application of GMM for background subtraction and motion analysis in video streams, particularly useful in scenarios like traffic surveillance.

## Overview

The project employs Gaussian Mixture Models to differentiate between the background and foreground in video frames. It is particularly adept at tracking objects in real-time within a fixed camera view, such as monitoring traffic through a surveillance camera.

### Dataset

The algorithm was tested on a 30-second traffic IP camera video from YouTube. This provided a realistic and challenging environment for object tracking.

## Methodology

1. **Video Processing**: The input video is processed using OpenCV to extract individual frames.
2. **Gaussian Mixture Modeling**: Each pixel value across all frames is modeled as a mixture of two Gaussians, representing the background and foreground.
3. **Background Construction**: The Gaussian with more weight and less standard deviation is used for constructing the background.
4. **Object Tracking**: Objects are tracked by subtracting the background from each frame.

## Algorithm

1. **Initialization**: Mean and variance values for both Gaussians are initialized.
2. **Likelihood Calculation**: Likelihood of each observation is calculated using initial mean and variance values.
3. **Probability Density Function**: Calculate PDF for both Gaussian clusters.
4. **Posterior Probability**: Using Bayes Theorem, we calculate the posterior probability for each Gaussian.
5. **Parameter Re-estimation**: The mean, variance, and weights of both Gaussians are iteratively updated until convergence.

## Limitations

- The implementation focuses more on demonstrating the concept rather than optimization for time complexity.
- The approach may struggle with foreground objects that are present for an extended duration.

## Results

The algorithm successfully segments moving objects from the background, as evidenced by the output frames and the final video demonstrating the moving object detection.

## Accuracy

The algorithm's performance was measured against OpenCV's BackgroundSubtractorMOG2 function using Mean Squared Error (MSE). The results show the effectiveness of the GMM approach in real-time object tracking.

## References

- [Gaussian Mixture Models Tutorial](https://towardsdatascience.com/how-to-code-gaussian-mixture-models-from-scratch-in-python-9e7975df5252)
- [Research Papers and Articles](URLs to the relevant papers and articles)

## Usage

Instructions on how to run and use the code can be found in the accompanying Jupyter notebook (`rtod_gmm.ipynb`).

## Contributing

Contributions to this project are welcome. Please refer to the contributing guidelines for more information.

## License
This project is open-source and available under the MIT License.
