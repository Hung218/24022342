# Phân loại ảnh CIFAR-100: Đánh giá Đa mô hình & Tiêu điểm ResNet-50

Repo này lưu trữ Notebook thực nghiệm phân loại tập dữ liệu **CIFAR-100**, so sánh giữa các kiến trúc CNN truyền thống và các mô hình Transformer hiện đại.

## Nội dung thực nghiệm
Notebook `Final.ipynb` thực hiện huấn luyện và so sánh đồng thời **6 cấu hình mô hình**:
1.  **SimpleCNN**: Mô hình cơ sở (Baseline).
2.  **VGG-19 (Scratch)**: Huấn luyện từ đầu trên ảnh 32x32.
3.  **VGG-19 (Fine-tune)**: Tinh chỉnh từ trọng số ImageNet (224x224).
4.  **ResNet-50 (Scratch)**: Huấn luyện từ đầu trên ảnh 32x32.
5.  **ResNet-50 (Fine-tune)**: Tinh chỉnh từ trọng số ImageNet (224x224).
6.  **CoCa (Transformer)**: Mô hình đa phương thức tiên tiến.

---

## Kết quả tổquát
Dưới đây là bảng so sánh hiệu năng trích xuất từ quá trình thực nghiệm:

| Mô hình | Chiến lược | Accuracy | Ghi chú |
| :--- | :--- | :--- | :--- |
| **ResNet-50** | **Fine-tuning** | **81.99%** | **Mô hình đề xuất** |
| CoCa | Fine-tuning | 74.83% | Transformer SOTA |
| VGG-19 | Fine-tuning | 73.93% | Pre-trained |
| ResNet-50 | Scratch | 71.72% | Huấn luyện từ đầu |
| VGG-19 | Scratch | 64.53% | Huấn luyện từ đầu |
| SimpleCNN | Scratch | 52.94% | Baseline |

---

## Lý do lựa chọn ResNet-50 cho báo cáo chuyên sâu
Mặc dù Notebook thực hiện huấn luyện đa dạng các mô hình, kiến trúc **ResNet-50 ** được lựa chọn làm trọng tâm báo cáo vì những lý do sau:

1.  **Hiệu năng vượt trội:** ResNet_50 (Fine_tuning) Đạt độ chính xác cao nhất (81.99%), vượt qua cả kiến trúc Transformer hiện đại là CoCa. Trong khi đó ResNet_50 (Scratch) cũng có kết quả vượt trội so với các kiến trúc được huấn luyện từ đầu khác.
2.  **Tính hiệu quả (Efficiency):** ResNet-50 (~23.5M tham số) nhỏ gọn hơn gấp 6 lần so với VGG-19 (>140M tham số) nhưng lại mang lại kết quả tốt hơn hẳn.
3.  **Độ ổn định:** Biểu đồ huấn luyện cho thấy ResNet-50 có tốc độ hội tụ nhanh nhất và đường Loss mượt mà nhất, chứng minh khả năng tối ưu hóa cực tốt của các kết nối Residual.

---

## Yêu cầu hệ thống
* **Framework:** PyTorch, Torchvision.
* **GPU:** Khuyến khích sử dụng Tesla P100 hoặc T4.
* **Dữ liệu:** Tự động tải thông qua Torchvision Datasets.

## 📂 Cấu trúc Repo
* `Final.ipynb`: Chứa toàn bộ code huấn luyện, biểu đồ so sánh (Bar chart, Line chart, Scatter plot) và log kết quả của 6 mô hình.
* `requirements.txt`: Yêu cầu phiên bản cho torch và torchvision. 
---
