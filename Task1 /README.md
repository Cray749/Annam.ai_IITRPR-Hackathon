# Soil Classification - Part 1

This repository contains the code and notebooks for the **Soil Classification Challenge** organized by Annam.ai at IIT Ropar. The goal is to build a **multi-class classifier** that can predict the specific soil type from an image.

---

## Project Structure

soil_classification_annam/
├── notebooks/ # Jupyter notebooks for training and inference
│ ├── training.ipynb
│ └── inference.ipynb
├── src/ # Source code (if any scripts/modules)
├── data/ # Dataset folder (data not included)
├── README.md # Project documentation
├── requirements.txt # Python dependencies
└── submission.csv # Final predictions ready for submission


---

## Getting Started

### Prerequisites

- Python 3.8+
- pip package manager

### Installation

1. Clone the repository:

```bash
git clone git@github.com:Nikieta/soil_classification_annam.git
cd soil_classification_annam
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

Open and run the notebooks/training.ipynb notebook to train the CNN model on soil images.

The notebook includes:

- Loading and preprocessing the multi-class labeled data
- Building a CNN model with Conv2D and Dense layers
- Training and evaluation using categorical cross-entropy loss
- Computing per-class F1-scores and classification report
- Saving the trained model



### Inference

Use the [notebooks/inference.ipynb](notebooks/inference.ipynb) notebook to load the saved model and make predictions on the test set.

The notebook generates a submission.csv file which can be submitted to the competition platform.

---

## Model Details

- The CNN model is a simple architecture with:
  - Two Conv2D layers
  - Flatten and Dense layers
  - Output layer with softmax activation for multi-class classification
  - A sigmoid output layer for binary classification
- Images are resized to **128x128** pixels
- Uses **binary cross-entropy loss** and **Adam optimizer**
- **F1-score** on the validation set is used to measure performance

---

## Evaluation

- Performance is reported using classification accuracy and detailed  classification reports.
- Per-class F1-scores are computed to assess the model's balance across soil categories.
- Final submissions require a CSV with image IDs and predicted soil types.



---

## References

- [TensorFlow Documentation](https://www.tensorflow.org/)
- [Keras Documentation](https://keras.io/)
- [Pillow (PIL) Documentation](https://pillow.readthedocs.io/en/stable/)

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
