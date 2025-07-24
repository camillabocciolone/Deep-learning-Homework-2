# Mars Terrain Segmentation with CNNs

This repository contains the code and results of the second homework for the course *Artificial Neural Networks and Deep Learning* (AN2DL), academic year 2024-2025, Politecnico di Milano.

The task is semantic segmentation of 64x128 grayscale images of Martian terrain, with 5 possible pixel-wise classes:
- Background
- Soil
- Bedrock
- Sand
- Big Rock

---

## 🧠 Summary of Approach

The project involved the design and training of several deep neural network architectures, with a focus on addressing class imbalance and segmentation accuracy.

- **Initial Models**: Basic U-Net and deep U-Net  
- **Loss Functions**: Focal Loss, Dice Loss, Boundary Loss, custom Weighted Sparse Categorical Crossentropy  
- **Architectures**: Dual U-Net, Attention U-Net  
- **Final Model**: Attention U-Net with Sparse Categorical Crossentropy (weighted)

---

## 📊 Results

| Model              | Val Mean IoU | Kaggle Score |
|-------------------|--------------|--------------|
| Basic U-Net       | 0.2301       | 0.23975      |
| Model 2 (custom loss) | 0.4573   | 0.45232      |
| Dual U-Net        | 0.4608       | 0.44973      |
| **Attention U-Net** | **0.6738**  | **0.68415**  |

- Best results achieved with Attention U-Net without additional loss weighting  
- Data augmentation using ImgAug helped improve generalization  
- Optimizer switched to AdamW with learning rate scheduling  

---

## ⚠️ Dataset

The file `mars_for_students.npz` contains the full dataset. It was provided by the course instructors.  
**Note:** The file is over 70MB and may not be ideal for long-term hosting on GitHub without using Git LFS.

---

## 📎 Authors

Camilla Bocciolone (`camibocciolone`)  
Davide Fileccia (`Davide Fileccia`)  
Luca Forte (`calu02`)  
Matilde Simonetti (`matisimonetti`)  

---

## 📁 Repository Structure

Mars-segmentation/  
├── Homework_2-3.pdf  
├── mars_for_students.npz  
├── notebooks/  
│   ├── Model1.ipynb  
│   └── Finalmodel.ipynb  
├── README.md  
