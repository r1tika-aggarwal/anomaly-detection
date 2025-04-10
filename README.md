# anomaly-detection
This project is a deep learning-based anomaly detection system for classifying Aadhaar card images as real or fake using autoencoders. The autoencoder is trained to reconstruct real Aadhaar images with minimal error. If a new input image cannot be reconstructed accurately it's flagged as fake.

## Overview

The model is designed to detect anomalies using the Mean Squared Error (MSE) between the original and reconstructed images. A higher MSE suggests the image is significantly different from the distribution of real Aadhaar cards and is likely to be fake.

## Model Details

- **Architecture**: Convolutional Autoencoder
- **Detection Method**: Reconstruction error (Mean Squared Error)
- **Thresholding**: Images with reconstruction error above a chosen threshold are classified as fake

## Dataset

**Note**: The dataset is **not included** in this repository.

- The original dataset was sourced from a Kaggle dataset (now unavailable).
- Additional Aadhaar images were collected from family and friends for training and testing.
- Extensive data augmentation was applied to improve model generalization, including transformations like rotation, flipping, cropping, brightness adjustments, and scaling.

## Setup Instructions

1. **Clone the repository**
git clone https://github.com/r1tika-aggarwal/anomaly-detection.git cd anomaly-detection

2. **Install dependencies**
pip install -r requirements.txt

3. **Prepare the dataset**

Create the following folder structure inside the `data/` directory:
data/ ├── train/real/ # Real Aadhaar images for training └── test/ ├── real/ # Real Aadhaar images for testing └── fake/ # Fake Aadhaar images for testing

4. **Train the model**
python autoencoder_model.py
or run the jupyter notebook in your browser

6. **Run anomaly detection on a test image**
change the url of the image to your own test image.

## Evaluation

- The model uses reconstruction loss (MSE) to determine whether an image is real or fake.
- During evaluation, a reconstruction threshold is chosen based on validation data.
- Images exceeding this threshold are flagged as fake.

## Notes

- This project is intended for educational and research purposes only.
- No Aadhaar card data is shared in this repository.
- Please ensure that any use of identity-related data complies with applicable legal and privacy regulations.

## Acknowledgements

- Kaggle community for the original dataset
- Contributors of anonymized Aadhaar images for testing and evaluation
