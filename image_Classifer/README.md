# Custom Image Classifier

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/xrealmayhem-ux/image_Classifer/blob/main/imageclassifier.ipynb)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![FastAI](https://img.shields.io/badge/FastAI-2.x-orange)](https://docs.fast.ai/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

An end-to-end deep learning pipeline that **automatically collects images from the web, cleans the dataset, and trains a fine-tuned ResNet18 classifier** — all in a single notebook. Just swap the search terms to classify anything you want.

---

##  Key Features

- **Automated Data Collection** — Scrapes training images directly from DuckDuckGo using the `ddgs` library. No manual dataset download required.
- **Built-in Data Cleaning** — Automatically detects and removes corrupted or invalid image files before training.
- **Transfer Learning** — Fine-tunes a pre-trained ResNet18 model for fast, high-accuracy results with minimal data.
- **Single Notebook Workflow** — From data collection to prediction in one file. Easy to replicate and modify.

---

##  Tech Stack

| Component | Tool |
|-----------|------|
| Framework | [FastAI](https://docs.fast.ai/) |
| Model | ResNet18 (pre-trained on ImageNet) |
| Data Source | DuckDuckGo Image Search via [`ddgs`](https://pypi.org/project/ddgs/) |
| Language | Python 3.10+ |
| Platform | Kaggle / Google Colab / Local |

---

##  Installation

### Option 1: Run in the Cloud (Recommended)
Click the **Open in Colab** badge above — no setup needed.

### Option 2: Run Locally
```bash
# Clone the repository
git clone https://github.com/xrealmayhem-ux/image_Classifer.git
cd image_Classifer

# Install dependencies
pip install fastai ddgs
```

---

##  Usage

1. **Open** `imageclassifier.ipynb` in Colab, Kaggle, or Jupyter.
2. **Modify the search terms** to classify any two categories:
   ```python
   searches = 'cat', 'dog'  # Change these to anything, e.g. 'bird', 'forest'
   ```
3. **Run all cells** — the notebook will:
   - Download ~200 images per category
   - Clean and resize the dataset
   - Train a ResNet18 classifier for 3 epochs
   - Run a prediction on a test image
4. **View the results** — the model prints the predicted label and confidence score.

---

##  Project Structure

```
image_Classifer/
├── imageclassifier.ipynb   # Main notebook (full pipeline)
├── README.md               # Project documentation
├── LICENSE                  # MIT License
└── .gitignore             
```

---

##  Results

The model achieves strong classification accuracy after just **3 epochs** of fine-tuning on ~200 images per class.

| Metric | Value |
|--------|-------|
| Architecture | ResNet18 |
| Fine-tune Epochs | 3 |
| Images per Class | ~200 |
| Validation Split | 20% |
| Image Size | 192 × 192 |

> **Note:** Accuracy varies depending on the categories chosen and the quality of images returned by the search engine.

---

##  Contributing

Contributions are welcome! Feel free to:

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  Made with ❤️ using <a href="https://docs.fast.ai/">FastAI</a>
</p>
