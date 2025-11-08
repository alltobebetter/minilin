# MiniLin Examples

This directory contains example scripts and notebooks demonstrating MiniLin's capabilities.

## 📚 Available Examples

### 1. Real-World IMDB Sentiment Analysis

**Files:**
- `imdb_sentiment_analysis.ipynb` - Interactive Jupyter notebook (recommended for Colab)
- `real_world_imdb.py` - Python script version

**What it demonstrates:**
- Loading real-world IMDB movie review dataset
- Few-shot learning with 200 samples
- Low-resource training with 1000 samples
- Model evaluation and comparison
- ONNX deployment
- Testing on custom reviews

**Quick Start (Notebook):**
```bash
# Open in Google Colab
# Upload imdb_sentiment_analysis.ipynb
# Click "Runtime" → "Run all"
```

**Quick Start (Script):**
```bash
# Install dependencies
pip install minilin datasets

# Run with default settings (1000 samples)
python examples/real_world_imdb.py

# Few-shot learning (200 samples)
python examples/real_world_imdb.py --samples 200 --epochs 5

# Standard training (5000 samples)
python examples/real_world_imdb.py --samples 5000 --epochs 3
```

**Expected Results:**
- 200 samples: ~75-80% accuracy in 2-3 minutes
- 1000 samples: ~85-88% accuracy in 5-8 minutes
- 5000 samples: ~90%+ accuracy in 15-20 minutes

---

### 2. Basic Text Classification

**File:** `text_classification.py`

Simple text classification example with synthetic data.

```bash
python examples/text_classification.py
```

---

### 3. Sentiment Analysis

**File:** `sentiment_analysis.py`

Sentiment analysis with custom data.

```bash
python examples/sentiment_analysis.py
```

---

### 4. Image Classification

**File:** `image_classification.py`

Image classification with CIFAR-10 or custom images.

```bash
python examples/image_classification.py
```

---

### 5. Audio Classification

**File:** `audio_classification.py`

Audio classification example.

```bash
python examples/audio_classification.py
```

---

### 6. Advanced Features

**File:** `advanced_features.py`

Demonstrates advanced MiniLin features:
- Custom data augmentation
- Model compression
- Hyperparameter tuning
- Multi-task learning

```bash
python examples/advanced_features.py
```

---

### 7. Multimodal Learning

**File:** `multimodal_example.py`

Multimodal learning with text and images.

```bash
python examples/multimodal_example.py
```

---

### 8. Custom Data

**File:** `custom_data.py`

How to use your own datasets with MiniLin.

```bash
python examples/custom_data.py
```

---

## 🚀 Running Examples

### Prerequisites

```bash
pip install minilin
```

### Optional Dependencies

For specific examples, you may need:

```bash
# For image examples
pip install minilin[vision]

# For audio examples
pip install minilin[audio]

# For all features
pip install minilin[all]
```

### Google Colab

All `.ipynb` notebooks can be run directly in Google Colab:

1. Go to [Google Colab](https://colab.research.google.com/)
2. Upload the notebook
3. Click "Runtime" → "Run all"

No local setup required!

---

## 📊 Benchmark Results

### IMDB Sentiment Analysis

| Samples | Strategy | Accuracy | Training Time | Model Size |
|---------|----------|----------|---------------|------------|
| 200     | Few-Shot | ~78%     | 2-3 min       | ~250 MB    |
| 1000    | Low-Res  | ~87%     | 5-8 min       | ~250 MB    |
| 5000    | Standard | ~91%     | 15-20 min     | ~250 MB    |

*Results may vary based on hardware and random seed*

---

## 💡 Tips

1. **Start Small**: Begin with few-shot learning (200 samples) to quickly validate your approach
2. **Use GPU**: Training is much faster with GPU (Colab provides free GPU)
3. **Adjust Epochs**: More data = fewer epochs needed
4. **Monitor Metrics**: Watch validation loss to avoid overfitting
5. **Try Augmentation**: MiniLin automatically applies data augmentation for small datasets

---

## 🐛 Troubleshooting

### Out of Memory

```python
# Reduce batch size
pipeline.train(batch_size=8)  # Default is 16
```

### Slow Training

```python
# Reduce epochs or samples
pipeline.train(epochs=2)
```

### Import Errors

```bash
# Install missing dependencies
pip install datasets  # For IMDB example
pip install matplotlib  # For visualization
```

---

## 📚 Learn More

- **Documentation**: See main [README.md](../README.md)
- **GitHub**: https://github.com/alltobebetter/minilin
- **PyPI**: https://pypi.org/project/minilin/

---

## 🤝 Contributing

Have a cool example? Submit a PR!

1. Create your example script/notebook
2. Add documentation here
3. Test it works
4. Submit PR

---

Made with ❤️ by the MiniLin Team
