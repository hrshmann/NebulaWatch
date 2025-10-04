dataset/

# 🚀 AstroGuard: Space Station Object Detection with YOLOv8

AstroGuard is an end-to-end object detection system for identifying **Toolbox**, **Oxygen Tank**, and **Fire Extinguisher** in space station environments, powered by YOLOv8 and synthetic data from Duality AI Falcon.

---

## 🌟 Features

- **YOLOv8 Training Pipeline** with hyperparameter optimization
- **Data Augmentation**: mosaic, HSV, flip, rotation, scaling
- **Comprehensive Evaluation**: mAP, confusion matrix, per-class metrics
- **Failure Case Analysis** and model improvement
- **Streamlit Web App**: real-time detection (image & webcam), analytics, downloads
- **Modular, Configurable, and GPU/CPU Compatible**

---

## 🚀 Quick Start

### Prerequisites

- Python 3.8+
- Anaconda/Miniconda
- CUDA GPU (recommended)

### Installation

```bash
git clone <repository-url>
cd space-station-object-detection
python setup.py
conda activate EDU
```

Or manually:

```bash
conda env create -f environment.yml
conda activate EDU
pip install tensorboard wandb albumentations
```

---

## 📁 Dataset Preparation

- Organize your data in `dataset/{train,val,test}/{images,labels}`
- Labels in YOLO format: `class_id x_center y_center width height` (normalized)
- Use `data_utils.py` for validation, analysis, splitting, and visualization

---

## �️ Training

Basic:

```bash
python train.py --config config.yaml --model-size n
```

Advanced:

```bash
python train.py --config config.yaml --model-size m --resume
```

Outputs: best/last model weights, training curves, logs.

---

## 📊 Evaluation

```bash
python predict.py --model runs/train/yolov8_training/weights/best.pt --config config.yaml
```

Generates confusion matrix, per-class metrics, and failure case analysis.

---

## 🌐 Web Application

Launch the Streamlit app:

```bash
streamlit run app.py
```

- Upload images or use webcam for detection
- Adjust confidence threshold and model selection
- View analytics and download results

---

## �️ Project Structure

```
├── config.yaml
├── environment.yml
├── setup.py
├── train.py
├── predict.py
├── app.py
├── data_utils.py
├── dataset/
├── runs/
├── logs/
├── models/
├── results/
```

---

## ⚙️ Configuration

Edit `config.yaml` for model, training, augmentation, and class settings.

---

## �️ Troubleshooting

- **CUDA OOM**: Reduce batch size
- **Poor Performance**: Try larger models, more augmentation, or more epochs
- **Dataset Issues**: Validate and analyze with `data_utils.py`

---

## 📈 Performance Targets

| Model    | mAP@0.5 | Speed (ms) | Memory (GB) |
|----------|---------|------------|-------------|
| YOLOv8n  | 85-90%  | 8.7        | 3.2         |
| YOLOv8s  | 88-92%  | 12.9       | 11.2        |
| YOLOv8m  | 90-94%  | 25.9       | 25.9        |
| YOLOv8l  | 92-96%  | 43.7       | 43.7        |

---

## 🤝 Contributing

1. Fork & branch
2. Make changes & add tests
3. Submit a pull request

---

## 📄 License

MIT License. See `LICENSE` for details.

---

## 🙏 Acknowledgments

- Ultralytics (YOLOv8)
- Duality AI (Falcon)
- Streamlit
- OpenCV

---

**Happy detecting! 🚀**