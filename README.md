# MRI-Image-Segmentation

## Giới thiệu
Repo này chứa mã nguồn của tôi cho cuộc thi [UW-Madison GI Tract Image Segmentation](https://www.kaggle.com/competitions/uw-madison-gi-tract-image-segmentation/overview). Trong cuộc thi này, người tham dự yêu cầu phải phân đoạn dữ liệu ảnh y khoa để giúp y bác sĩ trong việc điều trị cho bệnh nhân. Bên dưới là cách tôi thực hiện bài toán.
## Dataset
Dữ liệu cho cuộc thi bao gồm:
- **train**: một folder chứa dữ liệu ảnh của cuộc thi
- **train.csv**: chứa các trường dữ liệu của với tập huấn luyện
- **submission.csv**: định dạng file khi nộp kết quả

Thông tin chi tiết về dữ liệu có thể được tìm thấy [tại đây]([https://www.kaggle.com/competitions/global-wheat-detection/data](https://www.kaggle.com/competitions/uw-madison-gi-tract-image-segmentation/data)).

## Augmentation
Tăng cường dữ liệu nhiều lần:
- Resize
- Affine
- HorizontalFlip
- RandomBrightnessContrast
- GaussNoise

## Model
- UNet, với backbone Resnet50
- Dùng 5 fold cross validation
- Optimizer: Adam lr: 0.002
- Scheduler: CosineAnnealingLR, với T_max là 25 epoch
- Chạy 25 epoch

## Kaggle kernel
- [Code dùng để huấn luyện](https://www.kaggle.com/code/quntrnhongng/uwmgi-unet-training-pytorch-lightning)
- [Code dùng để infer](https://www.kaggle.com/code/quntrnhongng/uwmgi-unet-inference-pytorch)
