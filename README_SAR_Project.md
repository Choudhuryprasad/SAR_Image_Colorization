# SAR Image Colorization using Deep Learning

This project focuses on colorizing SAR (Synthetic Aperture Radar) grayscale satellite images into RGB color images using deep learning. The work aims to improve interpretability of SAR data for better visualization and downstream analysis.

---

## 🚀 Project Overview

**Objective**: Convert SAR grayscale images (S1) to colorized RGB images (S2) using a Pix2Pix-based conditional GAN model.

**Use Case**: This can help agricultural monitoring, disaster response, urban planning, and remote sensing applications by providing interpretable visuals of radar images.

---

## 🧠 Model Architecture

- **Pix2Pix GAN**: A conditional GAN (cGAN) architecture.
  - **Generator**: U-Net architecture
  - **Discriminator**: PatchGAN

---

## 🗂️ Dataset Structure

```
v_2/
  └── agri/
      ├── s1/        # SAR grayscale images
      │   ├── image_001.png
      │   └── ...
      └── s2/        # RGB ground truth images
          ├── image_001.png
          └── ...
```

- Images in `s1` and `s2` are **aligned** by filename.
- Preprocessing includes resizing, normalization to `[-1, 1]`.

---

## 🛠️ Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/sar-colorization.git
cd sar-colorization
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. If using pre-trained weights:

```bash
# Place generator.h5 and discriminator.h5 in `models/` directory
```

---

## 🏋️ Training

```bash
python train.py   --epochs 100   --batch_size 16   --input_path ./v_2/agri/s1   --target_path ./v_2/agri/s2
```

---

## 🖼️ Testing / Inference

```bash
python predict.py   --input_image ./v_2/agri/s1/test_image.png   --generator_path ./models/generator.h5   --output_path ./output/
```

---

## 📊 Evaluation Metrics

- SSIM (Structural Similarity Index)
- PSNR (Peak Signal-to-Noise Ratio)
- Visual Inspection

---

## 🌐 Web Interface (Optional)

A Streamlit-based web UI is available in `webapp/`:

```bash
cd webapp
streamlit run app.py
```

Upload SAR images and get real-time colorization output using the trained model.

---

## 🧪 Sample Results

| SAR Input | Predicted RGB | Ground Truth |
|-----------|----------------|---------------|
| ![](samples/sar.png) | ![](samples/pred.png) | ![](samples/gt.png) |

---

## 📁 Folder Structure

```
.
├── data/
│   └── v_2/agri/s1, s2
├── models/
│   └── generator.h5, discriminator.h5
├── scripts/
│   └── train.py, predict.py
├── webapp/
│   └── app.py
├── samples/
│   └── example visuals
└── README.md
```

---

## 👨‍💻 Author

**Rachet Khadiratna**  
B.Tech CSE, Gandhi Institute of Engineering and Technology University  
Aspiring Machine Learning Engineer

---

## 📜 License

This project is licensed under the MIT License.

---

## 📬 Contact

For queries, collaboration, or feedback:  
📧 rachet@example.com  
📱 +91-XXXXXXXXXX