
## Proses Pelatihan dengan Convolutional Neural Network (CNN)

Proyek ini menggunakan arsitektur **Convolutional Neural Network (CNN)** untuk mendeteksi penyakit. Model dibangun dengan menggunakan TensorFlow dan Keras, serta memanfaatkan augmentasi data untuk meningkatkan performa model. Berikut adalah detail dari proses pelatihan:

### 1. **Preprocessing Data**
- Data Normalization: Pixel values are normalized to a range of 0–1 using the rescale=1.0/255 parameter.
- Data Augmentation: Transformations such as rotation (up to 20°), horizontal and vertical shifts (up to 20%), shear (up to 20%), zoom (up to 20%), and horizontal flips were applied to increase data diversity.
- Dataset Splitting: The dataset was divided into 80% training and 20% validation data using **validation_split=0.2.**

### 2. **Arsitektur Model CNN**

- The CNN model comprises four convolutional layers with ReLU activation and filters of size 256, 128, 128, and 64, each followed by MaxPooling2D layers with a pool size of (2x2). The feature maps are flattened into a 1D vector, passed through a dense layer with 32 neurons (ReLU activation), and classified into 4 categories using a softmax activation function.  


### 3. **Parameter Pelatihan**
- Optimizer: Adam optimizer with a learning rate of 0.001.
- Loss Function: Categorical Crossentropy
- Metrics: Accuracy
- Batch Size: 32
- Number of Epochs: 50-60
## Hasil Training Model

| **Epoch** | **Training Accuracy** | **Training Loss** | **Validation Accuracy** | **Validation Loss** | **Deskripsi**                                      |
|-----------|------------------------|-------------------|--------------------------|---------------------|---------------------------------------------------|
| 50        | 92.68%                | 0.2347            | 92.49%                  | 0.2123              | Model mulai menunjukkan performa yang baik, namun masih dapat ditingkatkan.              |
| **60**        | **97.01%**                | **0.1336**            | **96.05%**                  | **0.1439**              | **Model memiliki performa terbaik dengan validation accuracy tertinggi dan validation loss terendah.** |
| 70        | 93.97%                | 0.1794            | 93.68%                  | 0.1792              | Validation accuracy menurun dibanding epoch 60, kemungkinan tanda awal overfitting.      |
| 80        | 93.53%                | 0.3162            | 93.68%                  | 0.2103              | Validation loss meningkat, menunjukkan model terlalu kompleks dan overfitting terjadi.   |
| 90        | 94.22%                | 0.1396            | 94.47%                  | 0.1511              | Validation accuracy meningkat kembali, tetapi validation loss sedikit lebih tinggi dari epoch 60. |

* [Augmented Lettuce Disease](https://drive.google.com/drive/folders/1bhB271ddAAcfuHirvlMnS0ssrSFt3MN8?usp=sharing)
* [Original Dataset](https://www.kaggle.com/datasets/ashishjstar/lettuce-diseases)
