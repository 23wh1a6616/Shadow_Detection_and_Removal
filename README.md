# 🌑 Real-Time Shadow Detection and Removal Using U-Net

A **deep learning-based shadow detection and removal system** that identifies shadows in images and produces a **shadow-free output** using a **U-Net architecture**. The project uses image processing techniques along with deep learning to improve the visual quality of images affected by shadows.

---

## 🚀 Features

* 🔍 **Detect shadows** present in input images
* 🧹 **Remove shadows** while preserving the original scene
* 🧠 Uses a **U-Net deep learning architecture**
* 🎯 Trained using the **ISTD (Image Shadow Triplets Dataset)**
* 🖼️ Uses **OpenCV** for image preprocessing and processing
* 📉 Uses **L1 Loss** for pixel-level reconstruction
* 🎨 Uses **Perceptual Loss** to preserve visual details
* ⚡ Designed for **real-time shadow removal**

---

## 🛠️ Technologies Used

| Technology       | Purpose                                |
| ---------------- | -------------------------------------- |
| **Python**       | Programming Language                   |
| **TensorFlow**   | Deep Learning Framework                |
| **U-Net**        | Shadow Detection & Removal Model       |
| **OpenCV**       | Image Processing                       |
| **NumPy**        | Numerical Computation                  |
| **VGG19**        | Feature Extraction for Perceptual Loss |
| **ISTD Dataset** | Model Training & Evaluation            |

---

## 🧠 How It Works

The system takes an image containing shadows as input and processes it through a deep learning pipeline.

```text
Input Image
     ↓
Image Preprocessing
     ↓
U-Net Model
     ↓
Shadow Detection
     ↓
Shadow Removal
     ↓
Post-processing
     ↓
Shadow-Free Image
```

The model learns the difference between **shadowed and shadow-free regions** and generates an output that minimizes the visual effect of shadows while maintaining important details.

---

## 🏗️ U-Net Architecture

The project uses the **U-Net architecture**, which is widely used for image-to-image tasks.

```text
                 INPUT IMAGE
                      │
                      ▼
              ┌─────────────┐
              │   Encoder   │
              └─────────────┘
                      │
                      ▼
               ┌───────────┐
               │ Bottleneck│
               └───────────┘
                      │
                      ▼
              ┌─────────────┐
              │   Decoder   │
              └─────────────┘
                      │
                      ▼
              SHADOW-FREE IMAGE
```

### 🔽 Encoder

The **encoder** extracts important features from the input image.

It learns information such as:

* Edges
* Textures
* Shapes
* Shadow patterns
* Spatial features

### 🔄 Bottleneck

The **bottleneck** contains the most compressed representation of the image.

It captures the **high-level features** required by the decoder to reconstruct the image.

### 🔼 Decoder

The decoder gradually reconstructs the image while recovering spatial information.

### 🔗 Skip Connections

U-Net uses **skip connections** between the encoder and decoder.

These connections help preserve:

* Fine details
* Edges
* Spatial information
* Image structure

This is particularly important for shadow removal because removing a shadow should **not destroy the details underneath it**.

---

## 📊 Dataset

The project uses the **ISTD (Image Shadow Triplets Dataset)**.

The dataset contains triplets consisting of:

* 🌑 **Shadow Image** – image containing shadows
* ☀️ **Shadow-Free Image** – corresponding image without shadows
* 🎭 **Shadow Mask** – identifies the shadow regions

The dataset allows the model to learn how shadowed images should be transformed into their corresponding shadow-free images.

---

## 📉 Loss Functions

The model uses multiple loss functions to improve the quality of the generated image.

### 1. L1 Loss

**L1 Loss** measures the pixel-level difference between the predicted image and the ground-truth shadow-free image.

```text
L1 Loss = |Predicted Image - Ground Truth|
```

It encourages the generated image to be **pixel-wise similar** to the expected output.

---

### 2. Perceptual Loss

Perceptual loss compares **high-level image features** rather than only individual pixels.

The project uses **VGG19** to extract feature representations from the generated and ground-truth images.

This helps preserve:

* **Textures**
* **Edges**
* **Shapes**
* **Visual details**

---

## 🎯 Training Process

The model is trained using shadowed images and their corresponding shadow-free images.

```text
Shadow Image
     │
     ▼
   U-Net
     │
     ▼
Predicted Shadow-Free Image
     │
     ▼
Compare with Ground Truth
     │
     ├── L1 Loss
     │
     └── Perceptual Loss
              │
              ▼
       Update Model Weights
```

The losses are used to calculate the error and update the network's weights during training.

---

## 🖼️ Input and Output

### Input

An image containing visible shadows.

### Output

A reconstructed image where the shadows are reduced or removed while attempting to preserve the original scene details.

```text
Input Image
     ↓
🌑 Shadow Present
     ↓
Deep Learning Model
     ↓
☀️ Shadow-Free Output
```

---

## 💡 Why U-Net?

U-Net is suitable for this project because shadow removal is an **image-to-image transformation problem**.

The architecture combines:

* **Encoder:** Understands the image and shadow patterns
* **Bottleneck:** Captures high-level information
* **Decoder:** Reconstructs the image
* **Skip Connections:** Preserve fine-grained details

This allows the model to remove shadows while maintaining the structure of the original image.

---

## 🖥️ Role of OpenCV

**OpenCV** is used for image-related operations such as:

* Reading images
* Resizing images
* Image preprocessing
* Converting image formats
* Saving processed images
* Supporting image input/output operations

---

## 📂 Project Structure

```text
Shadow-Removal/
│
├── dataset/
│   ├── train/
│   ├── test/
│   └── ...
│
├── models/
│   └── ...
│
├── preprocessing/
│   └── ...
│
├── train.py
├── predict.py
├── model.py
├── requirements.txt
└── README.md
```

> **Note:** Update the file names above if your actual repository uses different names.

---

## ⚙️ Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/23wh1a6616/<repository-name>.git
cd <repository-name>
```

### 2️⃣ Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

### Train the Model

```bash
python train.py
```

### Perform Shadow Removal

```bash
python predict.py
```

Provide an input image containing shadows and the trained model will generate the corresponding shadow-reduced/shadow-free output.

> **Note:** Update the commands according to the actual scripts in your repository.

---

## 📈 Applications

This project can be useful in:

* 📷 **Photography**
* 🏛️ **Heritage and monument imaging**
* 🛰️ **Remote sensing**
* 🚗 **Autonomous vision systems**
* 🖼️ **Image restoration**
* 🔬 **Computer vision research**
* 📱 **Mobile image enhancement**

---

