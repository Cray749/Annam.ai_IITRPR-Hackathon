# Soil Classification - Part 2

This repository contains the code and notebooks for the **Soil Classification Challenge** organized by Annam.ai at IIT Ropar. The goal is to build a binary classifier that can predict whether an image contains soil or not.

---

## Overview

Soil classification is crucial for agriculture, environmental assessment, and land management. This project uses **Convolutional Neural Networks (CNNs)** to classify soil images using the dataset provided by the challenge.

---

## Project Structure

```
soil_classification_part2_annam/
├── notebooks/              # Jupyter notebooks for training and inference
│   ├── training.ipynb
│   └── inference.ipynb
├── src/                    # Source code (if any scripts/modules)
├── data/                   # Dataset download script and data folder (data not included)
│   └── download.sh         # Script to download data from Kaggle
├── docs/cards/             # Documentation or cards (optional)
├── README.md               # Project documentation
├── requirements.txt        # Python dependencies
└── submission.csv          # Final predictions ready for submission
```

---

## Getting Started

### Prerequisites

- Python 3.8+
- `pip` package manager

### Installation

1. Clone the repository:

```bash
git clone git@github.com:Nikieta/soil_classification_part2_annam.git
cd soil_classification_part2_annam
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Download the dataset using the provided script (requires Kaggle API key):

```bash
cd data
bash download.sh
```

---

## Usage

### Training

Open and run the [`notebooks/training.ipynb`](notebooks/training.ipynb) notebook to train the CNN model on the soil images.

The notebook includes:

- Loading and preprocessing the data
- Model building (CNN)
- Training and validation
- Model saving

### Inference

Use the [`notebooks/inference.ipynb`](notebooks/inference.ipynb) notebook to load the saved model and make predictions on the test set.

The notebook generates a `submission.csv` file which can be submitted to the competition platform.

---

## Model Details

- The CNN model is a simple architecture with:
  - Two `Conv2D` layers
  - `MaxPooling`
  - A `Dense` layer
  - A sigmoid output layer for binary classification
- Images are resized to **128x128** pixels
- Uses **binary cross-entropy loss** and **Adam optimizer**
- **F1-score** on the validation set is used to measure performance

---

## Evaluation

- The competition uses the **F1-score** metric to evaluate submissions.
- The final submission should be a CSV with two columns:
  - `image_id`
  - `is_soil` (1 if soil, 0 if not)

---

## References

- [TensorFlow Documentation](https://www.tensorflow.org/)
- [Keras Documentation](https://keras.io/)
- [Pillow (PIL) Documentation](https://pillow.readthedocs.io/en/stable/)

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
