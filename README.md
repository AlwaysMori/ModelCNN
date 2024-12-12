
## Proses Pelatihan dengan Convolutional Neural Network (CNN)

Proyek ini menggunakan arsitektur **Convolutional Neural Network (CNN)** untuk mendeteksi penyakit pada tanaman selada. Model dibangun dengan menggunakan TensorFlow dan Keras, serta memanfaatkan augmentasi data untuk meningkatkan performa model. Berikut adalah detail dari proses pelatihan:

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

| **Epoch** | **Akurasi Training** | **Loss Training** | **Loss Validasi** | **Akurasi Validasi** | **Catatan**                     |
|-----------|-----------------------|-------------------|-------------------|-----------------------|----------------------------------|
| 50        | 0.9268               | 0.2347            | 0.2123            | 0.9249                | Hasil awal dari pelatihan model. |
| 60        | 0.9701               | 0.1336            | 0.1439            | 0.9605                | Akurasi meningkat dibandingkan sebelumnya. |
| 70        | 0.9658               | 0.1210            | 0.1104            | 0.9644                | Peningkatan signifikan pada performa model. |
| 80        | 0.9746               | 0.0824            | **0.0945**        | **0.9723**            | Model dengan performa terbaik. |
| 90        | 0.9422               | 0.1396            | 0.1512            | 0.9447                | Terjadi overfitting pada model. |
