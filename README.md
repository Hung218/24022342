# Phân loại ảnh trên tập dữ liệu CIFAR-100: Scratch vs. Fine-tuning

Dự án này thực hiện một nghiên cứu so sánh toàn diện về hiệu năng của các kiến trúc mạng nơ-ron khác nhau trên tập dữ liệu CIFAR-100 đầy thách thức.

## 📌 Tổng quan dự án
Mục tiêu chính là đánh giá hai chiến lược huấn luyện quan trọng trong Deep Learning:
1. **Huấn luyện từ đầu (Training from Scratch)**: Xây dựng và huấn luyện mô hình với trọng số ngẫu nhiên trên ảnh gốc 32x32 (SimpleCNN, VGG19, ResNet50).
2. **Tinh chỉnh (Fine-tuning)**: Sử dụng các mô hình Pre-trained (VGG19, ResNet50, CoCa) đã học từ các tập dữ liệu khổng lồ, sau đó tinh chỉnh trên ảnh CIFAR-100 đã được resize lên 224x224.

## 🏗️ Các mô hình được so sánh
- **SimpleCNN**: Mô hình cơ sở (Baseline) tự xây dựng với 3 lớp tích chập.
- **VGG19 & ResNet50**: Đại diện cho kiến trúc CNN sâu truyền thống (đánh giá cả hai phương pháp Scratch và Fine-tuning).
- **CoCa (ViT-B-32)**: Mô hình hiện đại (Foundation Model) từ OpenCLIP, kết hợp giữa Vision Transformer và ngôn ngữ.

## 📊 Kết quả thực nghiệm chính
| Mô hình | Chiến lược | Độ chính xác (Test Acc) | Tham số (Params) |
| :--- | :--- | :--- | :--- |
| **CoCa_Finetune** | Fine-tuning | XX.XX% | 512-dim |
| **ResNet50_Finetune** | Fine-tuning | XX.XX% | 23.5M |
| **SimpleCNN** | Scratch | 49.40% | ~1.0M |
| ... | ... | ... | ... |

*(Lưu ý: Bạn hãy điền các con số chính xác từ bảng kết quả cuối cùng trong Notebook của bạn vào đây)*

## 📂 Cấu trúc thư mục
- `notebooks/`: Chứa file `final.ipynb`.
- `results/`: Chứa các biểu đồ PNG về Loss, Accuracy và bảng so sánh.
- `report.pdf`: Báo cáo chi tiết bằng tiếng Việt (8-12 trang).
- `requirements.txt`: Danh sách các thư viện cần thiết để chạy dự án.

## 🛠️ Hướng dẫn cài đặt và chạy
1. Sao chép kho lưu trữ:
   ```bash
   git clone [https://github.com/ten-cua-ban/ten-repository.git](https://github.com/ten-cua-ban/ten-repository.git)
