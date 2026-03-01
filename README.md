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
project-root/
│
├── data/
│ ├── images/ # Chứa ảnh X-quang
│ ├── text/ # Chứa file IMDB Dataset.csv
│ └── temporal/ # Chứa file CSV COVID-19
│
├── notebooks/
│ ├── 01_image_preprocessing.ipynb
│ ├── 03_text_preprocessing.ipynb
│ └── 04_temporal_preprocessing.ipynb
│
├── requirements.txt
└── README.md

### Bước 3: Chạy Notebook

1. Mở **Jupyter Notebook** hoặc **VS Code**.
2. Mở file `01_image_preprocessing.ipynb` để xem quy trình xử lý ảnh y tế.
3. Mở file `04_temporal_preprocessing.ipynb` để xem quy trình trích xuất đặc trưng chuỗi thời gian.

---

## 4. Tài nguyên bên ngoài

### Link tập dữ liệu gốc (Kaggle)

- [Chest X-Ray Dataset](https://www.kaggle.com/datasets/paulothymoney/chest-xray-pneumonia)
- [COVID-19 Time Series Dataset](https://www.kaggle.com/datasets/niketchauhan/covid-19-time-series-data)
