# LAB ASSIGNMENT 01: DATA PREPROCESSING

**Môn học:** Khai thác dữ liệu và ứng dụng

---

## 1. Thông tin nhóm

- **Thành viên 1:** Phạm Quang Thịnh - 23127485
- **Thành viên 2:** Lê Quốc Thiện - 23127481

---

## 2. Mô tả các tập dữ liệu sử dụng

### 2.1. Digital Image Data (Xử lý ảnh kỹ thuật số)

- **Tên tập dữ liệu:** Chest X-Ray Images (Pneumonia)
- **Mô tả:** Tập dữ liệu gồm các ảnh X-quang ngực dùng để chẩn đoán bệnh viêm phổi. Ảnh ở định dạng JPEG, kích thước không đồng nhất và độ phân giải cao. (Nhóm chỉ sử dụng tập test để thực hiện)
- **Nguồn (link tải đầy đủ dataset):**  
  [Kaggle - Chest X-Ray Images](https://www.kaggle.com/datasets/paulothymoney/chest-xray-pneumonia)

---

### 2.2. Tabular Data (Xử lý dữ liệu dạng bảng)

- **Tên tập dữ liệu:** Credit Card Transactions Fraud Detection
- **Mô tả:** Tập dữ liệu mô phỏng các giao dịch thẻ tín dụng bao gồm thông tin khách hàng, người bán, giá trị giao dịch và tọa độ địa lý nhằm mục đích phát hiện hành vi gian lận (`is_fraud`).
- **Lưu ý quan trọng:** Do tệp dữ liệu `fraudTrain.csv` có dung lượng rất lớn, nhóm không thể đính kèm trực tiếp trong bộ mã nguồn. **Người dùng vui lòng truy cập link nguồn Kaggle bên dưới, tải tệp `fraudTrain.csv` về và đặt vào thư mục `data/tabular/` trước khi thực thi.**
- **Kỹ thuật thực hiện:** Xử lý dữ liệu thiếu (Median, K-NN Imputer), Chuẩn hóa (Min-Max, Standard, Robust Scaling), Mã hóa (One-hot, Frequency, Target Encoding) và Lựa chọn đặc trưng (Correlation Matrix, Feature Importance, RFE).
- **Nguồn:** [Kaggle - Fraud Detection Dataset](https://www.kaggle.com/datasets/kartik2112/fraud-detection)

---

### 2.3. Textual Data (Xử lý dữ liệu văn bản)

- **Tên tập dữ liệu:** IMDB Dataset of 50K Movie Reviews
- **Mô tả:** Chứa 50,000 đánh giá phim trên trang IMDB với nhãn cảm xúc (tích cực/tiêu cực). Dữ liệu thô chứa nhiều thẻ HTML và nhiễu.
- **Kỹ thuật thực hiện:** Làm sạch HTML, Tokenization (Word, Sentence, Subword), Stopwords removal, Stemming/Lemmatization và Vectorization (BoW, TF-IDF, Word2Vec).
- **Nguồn:** [Kaggle - IMDB Dataset](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)

---

### 2.4. Temporal Data (Dữ liệu chuỗi thời gian)

- **Tên tập dữ liệu:** COVID-19 Time Series Data
- **Mô tả:** Chứa số liệu thống kê hàng ngày về số ca nhiễm xác nhận, tử vong và hồi phục của đại dịch COVID-19 trên toàn cầu từ tháng 01/2020 đến tháng 10/2020.
- **Nguồn:**  
  [Kaggle - COVID-19 Time Series Data](https://www.kaggle.com/datasets/niketchauhan/covid-19-time-series-data)

---

## 3. Hướng dẫn cài đặt và thực thi

### Bước 1: Chuẩn bị môi trường

Yêu cầu máy tính đã cài đặt **Python 3.11 trở lên**.  
Khuyến khích sử dụng môi trường ảo (venv hoặc conda).

Cài đặt các thư viện cần thiết:

```bash
pip install -r requirements.txt

```

### Bước 2: Tổ chức thư mục

Đảm bảo cấu trúc thư mục như sau để tránh lỗi đường dẫn:

```text
project-root/
│
├── data/
│   ├── images/          # Chứa ảnh X-quang
│   ├── tabular/         # Đặt file fraudTrain.csv tải từ Kaggle vào đây
│   ├── text/            # Chứa file IMDB Dataset.csv
│   └── temporal/        # Chứa file CSV COVID-19
│
├── notebooks/
│   ├── 01_image_preprocessing.ipynb
│   ├── 02_tabular_preprocessing.ipynb
│   ├── 03_text_preprocessing.ipynb
│   └── 04_temporal_preprocessing.ipynb
│
├── requirements.txt
└── README.md
```

### Bước 3: Chạy Notebook

1. Mở ứng dụng **Jupyter Notebook**, **JupyterLab** hoặc **VS Code**.
2. Thực thi các tệp notebook trong thư mục `notebooks/` theo thứ tự hoặc tùy theo nhu cầu phân tích kỹ thuật:

- **`01_image_preprocessing.ipynb`**: Thực hiện quy trình xử lý ảnh y tế bao gồm: thay đổi kích thước (Resizing), chuẩn hóa Pixel (Normalization) và trích xuất đặc trưng hình thái (Edge Detection).
- **`02_tabular_preprocessing.ipynb`**: Thực hiện quy trình xử lý dữ liệu bảng bao gồm: xử lý dữ liệu thiếu (Imputation), chuẩn hóa thang đo (Robust Scaling), mã hóa biến phân loại (Target/Frequency Encoding) và lựa chọn đặc trưng tối ưu.
- **`03_text_preprocessing.ipynb`**: Thực hiện quy trình xử lý ngôn ngữ tự nhiên bao gồm: làm sạch văn bản, tách từ (Tokenization), chuẩn hóa từ (Lemmatization) và chuyển đổi văn bản thành vector (TF-IDF, Word2Vec).
- **`04_temporal_preprocessing.ipynb`**: Thực hiện quy trình xử lý dữ liệu thời gian bao gồm: định dạng chuỗi thời gian, xử lý khoảng trống dữ liệu (Interpolation), tái lấy mẫu (Resampling) và tạo đặc trưng trễ (Lag Features).

---

## 4. Tài nguyên bên ngoài

### Link tập dữ liệu gốc (Kaggle)

Dưới đây là các nguồn dữ liệu được sử dụng trong bài tập này:

- **Digital Image Data:** [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)
- **Tabular Data:** [Credit Card Transactions Fraud Detection](https://www.kaggle.com/datasets/kartik2112/fraud-detection)
- **Textual Data:** [IMDB Dataset of 50K Movie Reviews](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)
- **Temporal Data:** [COVID-19 Time Series Data](https://www.kaggle.com/datasets/niketchauhan/covid-19-time-series-data)

```

```
