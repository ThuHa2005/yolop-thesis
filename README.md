# YOLOP - Autonomous Driving Perception (Thesis)

Huấn luyện mô hình YOLOP cho bài toán nhận thức cảnh quan lái xe tự động.  
Nhóm 8 — Khoa Vật Lý, ĐHKHTN — ĐHQGHN, 2026.

## Kết quả (BDD100K val, 10,000 ảnh)

| Task | Metric | Nhóm | Pretrained (test lại) | Paper gốc |
|------|--------|:----:|:---------------------:|:---------:|
| Drivable Area | mIoU | **89.8%** | 89.2% | 91.5% |
| Lane Line | IoU | **45.7%** | 38.4% | 70.5% |
| Object Detection | mAP@0.5 | **76.1%** | 76.5% | 76.5% |
| Inference | FPS | **87.7** | - | 41 |

## Training Curves
![Training Curves](yolop_training_curves%20(1).png)

## Chiến lược huấn luyện
- **Giai đoạn 1:** Epoch 1–89, BDD100K (70k ảnh), train from scratch
- **Giai đoạn 2:** Epoch 90–118, BDD45K (35k ảnh), resume từ epoch 89
- Fix NMS tại epoch 89: conf threshold 0.001 → 0.3
- GPU: Kaggle Tesla T4 × 2, Batch size: 24, Optimizer: Adam LR=0.001


## Demo

Clone repo gốc YOLOP:
```bash
git clone https://github.com/hustvl/YOLOP.git
cd YOLOP
pip install -r requirements.txt
```

Download weights: [epoch-117.pth](https://drive.google.com/file/d/1aO5aUmC3QLAJLxpdT0W-6r8oAEDaFTmc/view?usp=sharing)
Đặt file `.pth` vào thư mục `weights/`.
Download video/ảnh muốn test đặt vào 'inference/videos/'
Chạy inference trên video:
```bash
python tools/demo.py --source inference/videos/your_video.mp4 --save-dir inference/output 
```
## Thành viên nhóm
| Họ tên | MSSV |
|--------|------|
| Nguyễn Thị Thu Hà | 23001603 |
| Triệu Quốc Khánh | 23001615 |
| Lê Văn Đạt | 23001592 |
| Triệu Đình Dũng | 23001587 |

## Tài liệu tham khảo
- [YOLOP paper](https://arxiv.org/abs/2108.11250)
- [BDD100K dataset](https://bdd-data.berkeley.edu/)
