# Setup Guide

This guide will help you set up the Horse vs Human Classification project on your local machine.

## Prerequisites

Before you begin, ensure you have the following installed:

- **Python 3.7+** ([Download](https://www.python.org/downloads/))
- **pip** (comes with Python)
- **Git** ([Download](https://git-scm.com/downloads))
- **(Optional) CUDA** for GPU acceleration ([NVIDIA Guide](https://developer.nvidia.com/cuda-downloads))

## Installation Steps

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/horse-vs-human-classification.git
cd horse-vs-human-classification
```

### 2. Create a Virtual Environment

**On macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

**On Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Verify Installation

```bash
python -c "import tensorflow as tf; print('TensorFlow version:', tf.__version__)"
```

You should see the TensorFlow version printed without errors.

## Running the Project

### Option 1: Jupyter Notebook (Local)

1. Start Jupyter Notebook:
```bash
jupyter notebook
```

2. Navigate to `notebooks/horse_vs_human.ipynb` in your browser
3. Run cells sequentially (Shift + Enter)

### Option 2: Google Colab (Recommended for Beginners)

1. Go to [Google Colab](https://colab.research.google.com/)
2. Upload `horse_vs_human.ipynb`
3. Run all cells
4. No local setup required!

### Option 3: Convert to Python Script

```bash
jupyter nbconvert --to script notebooks/horse_vs_human.ipynb
python horse_vs_human.py
```

## GPU Support (Optional)

### For NVIDIA GPUs:

1. Install CUDA Toolkit and cuDNN ([Guide](https://www.tensorflow.org/install/gpu))
2. Install TensorFlow GPU:
```bash
pip install tensorflow-gpu
```

3. Verify GPU is detected:
```bash
python -c "import tensorflow as tf; print('GPUs:', tf.config.list_physical_devices('GPU'))"
```

## Troubleshooting

### Issue: ImportError for TensorFlow

**Solution:**
```bash
pip uninstall tensorflow
pip install tensorflow==2.10.0
```

### Issue: Module not found

**Solution:**
```bash
pip install --upgrade -r requirements.txt
```

### Issue: Jupyter kernel crashes

**Solution:**
```bash
pip install --upgrade ipykernel
python -m ipykernel install --user
```

### Issue: Out of memory (OOM) errors

**Solution:**
- Reduce batch size in the code
- Close other applications
- Use Google Colab with GPU runtime

### Issue: Dataset download fails

**Solution:**
- Check internet connection
- Manually download from:
  - Training: https://storage.googleapis.com/learning-datasets/horse-or-human.zip
  - Validation: https://storage.googleapis.com/learning-datasets/validation-horse-or-human.zip
- Extract to `data/` folder

## Project Structure Setup

Create the following directories if they don't exist:

```bash
mkdir -p notebooks data models images
```

## Next Steps

Once setup is complete:

1. Open the notebook
2. Run the training cells
3. Test predictions on custom images
4. Experiment with hyperparameters
5. Try the improvement suggestions

## Getting Help

- Check [Issues](https://github.com/yourusername/horse-vs-human-classification/issues)
- Read the [FAQ](#faq)
- Open a new issue with details

## FAQ

**Q: Which Python version should I use?**
A: Python 3.7 to 3.10 is recommended for TensorFlow 2.10+

**Q: Do I need a GPU?**
A: No, but it speeds up training significantly. Colab offers free GPU access.

**Q: How long does training take?**
A: On CPU: 10-15 minutes, On GPU: 2-5 minutes

**Q: Can I use my own images?**
A: Yes! See the prediction section in the notebook.

## Resources

- [TensorFlow Installation Guide](https://www.tensorflow.org/install)
- [Python Virtual Environments](https://docs.python.org/3/tutorial/venv.html)
- [Jupyter Notebook Basics](https://jupyter-notebook.readthedocs.io/en/stable/)

---

Happy coding! 🚀
