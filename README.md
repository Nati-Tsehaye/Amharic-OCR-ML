# Amharic OCR

This project implements an Optical Character Recognition (OCR) system for reading and interpreting Amharic text from images. It uses a Convolutional Neural Network (CNN) to recognize characters and translate them into readable text.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Model Architecture](#model-architecture)
- [Training](#training)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The Amharic language is one of the most widely spoken languages in Ethiopia. This project aims to provide a reliable OCR solution that can help digitize printed Amharic text, making it more accessible for various applications, including document analysis, digital libraries, and translation services.

## Dataset

The model is trained on a dataset of Amharic text images. The dataset consists of:

- Images of printed Amharic characters and words.
- Label files that correspond to the text within the images.

The dataset can be loaded from `.npy` files that contain both the images and their associated labels.

## Installation

To set up the environment for this project, follow these steps:

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd amharic-ocr
   ```

2. Create a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Training the Model

To train the model, execute the following command:
```bash
python train.py
```

Make sure to update the paths in `train.py` to point to your training data.

### Making Predictions

To use the trained model for predictions, run the following command:
```bash
python predict.py --image <path-to-image>
```

Replace `<path-to-image>` with the path to the image you want to process.

### Example

Here’s an example of how to use the prediction function in Python:
```python
from predict import predict_image

image_path = 'path/to/test_image.png'
predicted_text = predict_image(image_path)
print(f"Predicted Text: {predicted_text}")
```

## Model Architecture

The model architecture is based on a Convolutional Neural Network (CNN) designed for image classification tasks. The architecture consists of:

- Several convolutional layers for feature extraction.
- MaxPooling layers to reduce dimensionality.
- Fully connected layers for classification.

### Model Summary
```python
model.summary()
```

## Training

The model is trained using the following parameters:
- **Epochs**: 10 (can be adjusted)
- **Batch Size**: 32
- **Loss Function**: Sparse Categorical Crossentropy
- **Optimizer**: Adam

The training process can be monitored by inspecting the training logs printed to the console.

## Testing

To evaluate the performance of the model on unseen data, run the test script:
```bash
python test.py
```

## Contributing

Contributions are welcome! If you would like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes and commit them (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
