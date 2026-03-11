# Horse vs Human Image Classification

A deep learning project that uses Convolutional Neural Networks (CNN) to classify images as either horses or humans using TensorFlow and Keras.

##  Project Overview

This project implements a binary image classification model using deep learning to distinguish between images of horses and humans. The model is built using TensorFlow/Keras and achieves high accuracy through a multi-layer convolutional neural network architecture.

##  Objectives

- Build a CNN model from scratch for binary image classification
- Train the model to distinguish between horse and human images
- Implement data augmentation to improve model generalization
- Achieve high accuracy on the classification task
- Enable custom image prediction functionality

##  Project Structure

```
horse-vs-human-classification/
│
├── notebooks/
│   └── horse_vs_human.ipynb        # Main training notebook
│
├── data/                            # Dataset directory (downloaded during execution)
│   ├── horse-or-human/             # Training data
│   │   ├── horses/                 # Horse images
│   │   └── humans/                 # Human images
│   └── validation-horse-or-human/  # Validation data
│
├── models/                          # Saved model files (optional)
│
├── images/                          # Sample images and results
│
├── README.md                        # Project documentation (this file)
├── requirements.txt                 # Python dependencies
├── LICENSE                          # Project license
└── .gitignore                       # Git ignore file
```

##  Dataset

The project uses the **Horse or Human** dataset:

- **Training Set**: 1,027 images
  - Horse images: 500
  - Human images: 527
- **Image Size**: 300x300 pixels
- **Format**: RGB images
- **Source**: Google's Learning Datasets

Dataset is automatically downloaded from:
- Training: `https://storage.googleapis.com/learning-datasets/horse-or-human.zip`
- Validation: `https://storage.googleapis.com/learning-datasets/validation-horse-or-human.zip`

##  Model Architecture

The CNN model consists of:

```
Input Layer (300x300x3)
    ↓
Conv2D (16 filters, 3x3) + ReLU
    ↓
MaxPooling (2x2)
    ↓
Conv2D (32 filters, 3x3) + ReLU
    ↓
MaxPooling (2x2)
    ↓
Conv2D (64 filters, 3x3) + ReLU
    ↓
MaxPooling (2x2)
    ↓
Conv2D (64 filters, 3x3) + ReLU
    ↓
MaxPooling (2x2)
    ↓
Conv2D (64 filters, 3x3) + ReLU
    ↓
MaxPooling (2x2)
    ↓
Flatten
    ↓
Dense (512 neurons) + ReLU
    ↓
Dense (1 neuron) + Sigmoid
    ↓
Output (Binary Classification)
```

**Key Features:**
- Progressive feature extraction through multiple convolutional layers
- MaxPooling for dimensionality reduction
- RMSprop optimizer
- Binary crossentropy loss function
- Custom callback for early stopping at 99.9% accuracy

##  Technologies Used

- **Python 3.x**
- **TensorFlow 2.x**: Deep learning framework
- **Keras**: High-level neural networks API
- **NumPy**: Numerical computing
- **Matplotlib**: Data visualization
- **PIL (Pillow)**: Image processing
- **Google Colab**: Development environment (optional)

##  Getting Started

### Prerequisites

- Python 3.7 or higher
- pip package manager
- (Optional) GPU for faster training

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/horse-vs-human-classification.git
cd horse-vs-human-classification
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

### Running the Project

#### Option 1: Using Jupyter Notebook (Local)

```bash
jupyter notebook
```
Navigate to `notebooks/horse_vs_human.ipynb` and run all cells.

#### Option 2: Using Google Colab (Recommended)

1. Upload `horse_vs_human.ipynb` to Google Colab
2. Run all cells sequentially
3. The dataset will be downloaded automatically

#### Option 3: Python Script

Convert the notebook to a Python script:
```bash
jupyter nbconvert --to script notebooks/horse_vs_human.ipynb
python horse_vs_human.py
```

##  Training Process

1. **Data Loading**: Download and extract training and validation datasets
2. **Data Preprocessing**: 
   - Rescale pixel values to [0, 1]
   - Apply ImageDataGenerator for batch processing
3. **Model Training**: 
   - Train for up to 15 epochs
   - Use custom callback to stop at 99.9% accuracy
   - Batch size: 128 images
4. **Validation**: Evaluate model on validation set

### Training Parameters

- **Epochs**: 15 (with early stopping)
- **Steps per epoch**: 8
- **Optimizer**: RMSprop (lr=0.001)
- **Loss**: Binary Crossentropy
- **Metrics**: Accuracy

##  Results

The model achieves:
- **Training Accuracy**: ~99.9% (with early stopping)
- **Validation Accuracy**: Varies based on training run
- **Quick convergence**: Usually within 10-15 epochs

##  Making Predictions

You can test the model on custom images:

```python
from keras.preprocessing import image
import numpy as np

# Load and preprocess image
img = image.load_img('path_to_image.jpg', target_size=(300, 300))
x = image.img_to_array(img)
x = np.expand_dims(x, axis=0)
x = x / 255.0

# Predict
prediction = model.predict(x)
if prediction[0] > 0.5:
    print("It's a human!")
else:
    print("It's a horse!")
```

##  Visualizations

The notebook includes:
- Sample training images (4x4 grid of horses and humans)
- Training history plots (accuracy and loss curves)
- Prediction results on test images

##  Key Learnings

- **Convolutional layers** effectively extract spatial features from images
- **Data augmentation** (if implemented) helps prevent overfitting
- **Binary classification** can be achieved with a single sigmoid output neuron
- **Callbacks** enable custom training control (early stopping, learning rate scheduling)

##  Future Improvements

- [ ] Add data augmentation (rotation, flipping, zoom)
- [ ] Implement transfer learning with pre-trained models (VGG16, ResNet)
- [ ] Add confusion matrix and detailed metrics
- [ ] Create a web interface for real-time predictions
- [ ] Export model to TensorFlow Lite for mobile deployment
- [ ] Add more classes (different animals)
- [ ] Implement gradCAM for visualization

##  Contributing

Contributions are welcome! To contribute:

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

##  License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤Author

**Rohan Neupanee**

- GitHub: [@rohannp02y](https://github.com/rohannp02y)
- LinkedIn: [Rohan Neupane](www.linkedin.com/in/rohan-neupane)
- Email: your.email@example.com

##  Acknowledgments

- Dataset provided by Google's TensorFlow team
- Inspired by Laurence Moroney's TensorFlow courses
- TensorFlow and Keras documentation

## Resources

- [TensorFlow Documentation](https://www.tensorflow.org/)
- [Keras Documentation](https://keras.io/)
- [CNN Explainer](https://poloclub.github.io/cnn-explainer/)
- [Horse or Human Dataset](https://www.tensorflow.org/datasets/catalog/horses_or_humans)

##  Contact

For questions, suggestions, or collaboration opportunities, please open an issue or reach out via email.

---

⭐ **If you found this project helpful, please give it a star!**

##  Tags

`deep-learning` `computer-vision` `image-classification` `tensorflow` `keras` `cnn` `neural-networks` `machine-learning` `python` `binary-classification`
