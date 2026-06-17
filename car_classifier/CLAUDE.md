# Car Classifier Project

## Mô tả dự án

Dự án sử dụng Neural Network trong Deep Learning để phân loại hình ảnh thành 2 nhãn:
- **Xe ô tô** (car)
- **Không phải xe ô tô** (non-car)

## Công nghệ sử dụng

- **Framework**: PyTorch, torchvision
- **Ngôn ngữ**: Python
- **Môi trường**: Jupyter Notebook

## Cấu trúc dự án

```
car_classifier/
├── data/
│   ├── train/       # Dữ liệu huấn luyện
│   └── valid/       # Dữ liệu kiểm tra
├── models/          # Lưu model đã huấn luyện
├── notebooks/       # Các notebook thử nghiệm
├── src/
│   ├── crape.ipynb  # Notebook thu thập dữ liệu
│   ├── dataset.py   # Xử lý dataset
│   ├── model.py     # Định nghĩa kiến trúc model
│   ├── train.py     # Huấn luyện model
│   ├── evaluate.py  # Đánh giá model
│   └── utils.py     # Các hàm tiện ích
├── car_classifier.ipynb  # Notebook chính
└── requirements.txt
```

## Mục tiêu

Xây dựng mô hình phân loại nhị phân (binary classification) có khả năng nhận diện chính xác xe ô tô trong ảnh.
