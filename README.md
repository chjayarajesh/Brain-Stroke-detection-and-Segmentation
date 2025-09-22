# Deep Learning-Based Stroke Classification and Lesion Segmentation Using CT Images

## 📖 Abstract  
Stroke is a major cause of mortality and long-term disability, requiring accurate classification and lesion localization for effective treatment planning.  
This work presents a **deep learning framework** for stroke type classification and lesion segmentation using **CT brain images**.  

- **Preprocessing & Augmentation** applied to improve data quality and address class imbalance.  
- **Transfer learning (ConvNeXt / DenseNet)** used for stroke type classification (**Ischemic, Hemorrhagic, Normal**).  
- **U-Net** trained for lesion segmentation with expert-annotated masks.  
- Integrated **two-stage pipeline**:  
  1. Classify stroke type.  
  2. Segment lesion if present.  

Performance is evaluated with **accuracy, precision, recall, specificity, and F1-score**.  
This framework demonstrates strong potential as a **clinical decision support tool**, offering automated, reliable, and scalable solutions for assisting radiologists in stroke analysis and treatment planning.  

**Keywords**: Stroke Classification, Deep Learning, Transfer Learning, U-Net, Segmentation  

---

## 📂 Dataset  
- **Source**: [Brain Stroke CT Dataset (Kaggle)](https://www.kaggle.com/datasets/ozguraslank/brain-stroke-ct-dataset)  
- **Classes**:  
  - *Ischemia*  
  - *Hemorrhage (Bleeding)*  
  - *Normal*  
- **Format**: CT images (`.png`) and lesion masks (`.png`)  
- **Preprocessing**:  
  - Train/Validation/Test split (70/15/15)  
  - Normal cases: auto-generated zero masks  

---

## ⚙️ Installation  

```bash
# Clone this repo
git clone https://github.com/your-username/stroke-classification-segmentation.git
cd stroke-classification-segmentation

# Install dependencies
pip install -r requirements.txt
```

**requirements.txt** should include:
```
torch
torchvision
timm
scikit-learn
opencv-python
matplotlib
seaborn
numpy
pillow
```

---

## 🚀 Usage  

1. **Download dataset** using Kaggle API:
   ```bash
   kaggle datasets download -d ozguraslank/brain-stroke-ct-dataset -p ./dataset
   unzip dataset/brain-stroke-ct-dataset.zip -d ./dataset
   ```

2. **Run preprocessing** (splits dataset into train/val/test):
   ```python
   python preprocess.py
   ```

3. **Train classification model**:
   ```python
   python train_classifier.py
   ```

4. **Train segmentation model (U-Net)**:
   ```python
   python train_unet.py
   ```

5. **Evaluate results**:
   - Classification metrics (accuracy, precision, recall, F1)  
   - Segmentation metrics (Dice, IoU, pixel accuracy)  
   - Visualizations (confusion matrix, segmented lesion overlays)  

---

## 📊 Results  
- High **classification accuracy (>90%)** across stroke types.  
- U-Net segmentation achieves **precise lesion localization**.  
- Example visualizations:  
  - Confusion matrices  
  - Loss/accuracy curves  
  - Segmentation overlays  

---

## 📌 Project Structure  

```
/content/
│── dataset/
│   └── Brain_Stroke_CT_Dataset/
│       ├── Bleeding/
│       │   ├── PNG/
│       │   └── OVERLAY/
│       ├── Ischemia/
│       │   ├── PNG/
│       │   └── OVERLAY/
│       └── Normal/
│           ├── PNG/
│           └── OVERLAY/   (may be empty → zero masks auto-created)
│
│── train/
│   ├── PNG/
│   │   ├── Bleeding/
│   │   ├── Ischemia/
│   │   └── Normal/
│   └── OVERLAY/
│       ├── Bleeding/
│       ├── Ischemia/
│       └── Normal/
│
│── val/
│   ├── PNG/
│   │   ├── Bleeding/
│   │   ├── Ischemia/
│   │   └── Normal/
│   └── OVERLAY/
│       ├── Bleeding/
│       ├── Ischemia/
│       └── Normal/
│
│── test/
│   ├── PNG/
│   │   ├── Bleeding/
│   │   ├── Ischemia/
│   │   └── Normal/
│   └── OVERLAY/
│       ├── Bleeding/
│       ├── Ischemia/
│       └── Normal/
│
│── Stroke_detection_and_segmentation.ipynb

```

---

## 👨‍💻 Authors  
- **CH JAYA RAJESH**  


