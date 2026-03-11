# 🚀 Quick Start Guide

Get started with the Horse vs Human Classification project in 5 minutes!

## Option 1: Google Colab (Easiest - No Installation!)

1. **Open Google Colab**: Go to [colab.research.google.com](https://colab.research.google.com/)
2. **Upload Notebook**: Click `File` → `Upload notebook` → Select `horse_vs_human.ipynb`
3. **Run All**: Click `Runtime` → `Run all`
4. **Done!** The model will train automatically 🎉

## Option 2: Local Setup (5 Steps)

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/horse-vs-human-classification.git
cd horse-vs-human-classification

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Start Jupyter
jupyter notebook

# 5. Open horse_vs_human.ipynb and run all cells
```

## What the Model Does

- ✅ Downloads 1,000+ images of horses and humans
- ✅ Builds a Convolutional Neural Network (CNN)
- ✅ Trains the model (takes ~5-10 minutes)
- ✅ Achieves 99%+ accuracy
- ✅ Lets you test on your own images!

## Test Your Own Images

After training, you can classify your own images:

```python
# Upload an image and run prediction
from keras.preprocessing import image
import numpy as np

# Load image
img = image.load_img('your_image.jpg', target_size=(300, 300))
x = image.img_to_array(img)
x = np.expand_dims(x, axis=0)
x = x / 255.0

# Predict
prediction = model.predict(x)
if prediction[0] > 0.5:
    print("🧑 It's a human!")
else:
    print("🐴 It's a horse!")
```

## Common Questions

**Q: Do I need a powerful computer?**
A: No! Use Google Colab for free GPU access.

**Q: How long does training take?**
A: 5-10 minutes on Colab, 10-20 minutes on CPU.

**Q: Can I modify the code?**
A: Absolutely! That's the best way to learn.

**Q: What if I get errors?**
A: Check the [SETUP.md](SETUP.md) guide or open an issue.

## Next Steps

- 📖 Read the full [README.md](README.md)
- 🛠️ Follow detailed [SETUP.md](SETUP.md)
- 🤝 See [CONTRIBUTING.md](CONTRIBUTING.md) to contribute
- 🔬 Experiment with different architectures
- 📊 Add data augmentation
- 🌐 Deploy as a web app

## Need Help?

- 💬 Open an [Issue](https://github.com/yourusername/horse-vs-human-classification/issues)
- 📧 Email: your.email@example.com
- 🐦 Twitter: @yourhandle

---

Happy learning! 🎓✨
