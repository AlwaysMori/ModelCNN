
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
---
## Label

Dataset yang digunakan dalam proyek ini terdiri dari empat label berikut, yang masing-masing mewakili kategori kondisi tanaman selada:

1. **Healthy**: Gambar tanaman selada yang sehat dan bebas dari penyakit atau hama.
2. **Fungal**: Gambar tanaman selada yang terinfeksi penyakit jamur, seperti powdery mildew atau downy mildew.
3. **Bacterial**: Gambar tanaman selada yang terinfeksi penyakit bakteri, seperti bercak daun bakterial atau layu bakteri.
4. **Shepherd's Purse Weeds**: Gambar tanaman gulma yang tumbuh di antara tanaman selada, khususnya gulma shepherd's purse.


---
## Hasil Training Model
| **Epoch**               | **Training Accuracy**   | **Training Loss**       | **Validation Accuracy** | **Validation Loss**     | **Learning Rate**   | **Deskripsi**                                                                                                                                          | **Terpakai** |
|-------------------------|-------------------------|-------------------------|-------------------------|-------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| 50                      | 0.9399                  | 0.2625                  | 0.9332                  | 0.2407                  | 0.001               | **Epoch 50 (Learning Rate 0.001)**: Model menunjukkan akurasi pelatihan yang tinggi (0.9399) dan loss pelatihan rendah (0.2625), dengan akurasi validasi yang juga sangat baik (0.9332). | ✔            |
| 60                      | 0.9063                  | 0.2571                  | 0.9376                  | 0.1494                  | 0.001               | **Epoch 60 (Learning Rate 0.001)**: Meskipun akurasi pelatihan menurun sedikit menjadi 0.9063, akurasi validasi meningkat menjadi 0.9376, yang menunjukkan bahwa model lebih baik dalam menggeneralisasi data yang tidak terlihat sebelumnya. | ✘              |
| 50                      | 0.8030                  | 0.5106                  | 0.8103                  | 0.5064                  | 0.00001             | **Epoch 50 (Learning Rate 0.00001)**: Dengan learning rate yang lebih kecil, akurasi pelatihan dan validasi menurun secara signifikan. Akurasi pelatihan hanya mencapai 0.8030, dan loss pelatihan lebih tinggi (0.5106), menunjukkan pembelajaran yang lebih lambat dan kurang optimal dibandingkan dengan epoch lainnya. | ✘            |

---
