# Car Classifier — Deep Neural Network

Phân loại ảnh **xe ô tô** vs **không phải xe ô tô** sử dụng Deep Neural Network xây dựng từ đầu bằng NumPy (không dùng framework ML).

## Kiến trúc mô hình

```
Input (12288) → [LINEAR → RELU] × (L-1) → LINEAR → SIGMOID → Output (1)
```

- **Input**: ảnh 64×64×3 được flatten thành vector 12288 chiều
- **Hidden layers**: `[12288, 20, 7, 5, 1]` (có thể tùy chỉnh)
- **Output**: xác suất là xe ô tô (> 0.5 → car, ≤ 0.5 → non-car)
- **Loss**: Binary Cross-Entropy
- **Optimizer**: Gradient Descent

## Cấu trúc dự án

```
car_classifier/
├── data/
│   ├── train/
│   │   ├── car/        # 500 ảnh xe ô tô
│   │   └── non_car/    # 500 ảnh không phải xe
│   └── valid/
│       ├── car/        # 100 ảnh xe ô tô
│       └── non_car/    # 100 ảnh không phải xe
├── src/
│   ├── crape.ipynb     # Thu thập dữ liệu từ Kaggle
│   ├── dataset.py
│   ├── model.py
│   ├── train.py
│   ├── evaluate.py
│   └── utils.py
├── car_classifier.ipynb  # Notebook chính
└── requirements.txt
```

## Dataset

| Split    | Car  | Non-car | Tổng |
|----------|------|---------|------|
| Train    | 500  | 500     | 1000 |
| Validate | 100  | 100     | 200  |

- **Car**: [ryanholbrook/car-or-truck](https://www.kaggle.com/datasets/ryanholbrook/car-or-truck) (Kaggle)
- **Non-car**: [Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification) — buildings, forest, glacier, mountain, sea, street

## Cài đặt

```bash
pip install -r requirements.txt
```

## Sử dụng

Mở `car_classifier.ipynb` và chạy **Kernel → Restart & Run All**.

Notebook sẽ tự động:
1. Load và tiền xử lý ảnh (resize 64×64, normalize về [0, 1])
2. Huấn luyện mô hình 2500 iterations
3. Vẽ learning curve
4. In accuracy trên train set và validation set
5. Dự đoán trên ảnh tùy chọn

## Kết quả

| Dataset    | Accuracy |
|------------|----------|
| Train      | ~85%+    |
| Validation | ~75%+    |

> Kết quả có thể thay đổi tùy `layers_dims` và `num_iterations`.

## Công nghệ

- Python, NumPy, Matplotlib
- PIL (Pillow) — xử lý ảnh
- Jupyter Notebook
