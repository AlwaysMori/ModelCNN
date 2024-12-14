
## Proses Pelatihan dengan Convolutional Neural Network (CNN)

Proyek ini menggunakan arsitektur **Convolutional Neural Network (CNN)** untuk mendeteksi penyakit. Model dibangun dengan menggunakan TensorFlow dan Keras, serta memanfaatkan augmentasi data untuk meningkatkan performa model. Berikut adalah detail dari proses pelatihan:

### 1. **Preprocessing Data**
Dataset diproses menggunakan **ImageDataGenerator** untuk:
- **Normalisasi data**: Nilai piksel dinormalisasi menjadi rentang 0–1.
- **Augmentasi data**: Melakukan transformasi seperti rotasi, pergeseran, pemotongan, zoom, dan pembalikan horizontal untuk meningkatkan keragaman data pelatihan.
- Dataset dibagi menjadi **80% data pelatihan** dan **20% data validasi** menggunakan parameter `validation_split`.

### 2. **Arsitektur Model CNN**

- **Conv2D**: 32, 64, 128, 128 filter, kernel (3x3), ReLU activation.  
- **MaxPooling2D**: Pool size (2x2).  
- **Flatten**: Mengubah input menjadi vektor 1D.  
- **Dense**: Jumlah neuron sesuai kelas, Softmax activation.  


### 3. **Parameter Pelatihan**
- **Optimizer**: Adam
- **Loss Function**: Categorical Crossentropy
- **Metrics**: Akurasi
- **Batch Size**: 32
- **Jumlah Epoch**: 50 - 90
## Hasil Training Model

| **Epoch** | **Training Accuracy** | **Training Loss** | **Validation Accuracy** | **Validation Loss** | **Deskripsi**                                      |
|-----------|------------------------|-------------------|--------------------------|---------------------|---------------------------------------------------|
| 60        | 97.01%                | 0.1336            | 96.05%                  | 0.1439              | Model memiliki performa terbaik dengan validation accuracy tertinggi dan validation loss terendah. |
| 70        | 93.97%                | 0.1794            | 93.68%                  | 0.1792              | Validation accuracy menurun, kemungkinan tanda awal overfitting.                          |
| 80        | 93.53%                | 0.3162            | 93.68%                  | 0.2103              | Validation loss meningkat, menunjukkan model terlalu kompleks dan overfitting terjadi.   |


* [Augmented Lettuce Disease](https://drive.google.com/drive/folders/1bhB271ddAAcfuHirvlMnS0ssrSFt3MN8?usp=sharing)
* [Original Dataset](https://www.kaggle.com/datasets/ashishjstar/lettuce-diseases)
