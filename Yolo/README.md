# **YOLO - Object Detection**

- **Yolo 11 nano**
- Ultralytics YOLO version: 8.3.56
- PyTorch version: 2.4.1+cu118
- Pillow version: 10.4.0
- OpenCV version: 4.10.0
- Numpy version: 1.24.4

## Data
- original_images folder: orginal images
- images folder: preprocessed images
- label folder
- data.yaml

```
Data/
├── Original images/
│   ├── train/
│   │   ├── image1.png
│   │   ├── image2.png
│   │   └── ...
│   ├── val/
│   │   ├── image3.png
│   │   ├── image4.png
│   │   └── ...
├── images/
│   ├── train/
│   │   ├── image1.png
│   │   ├── image2.png
│   │   └── ...
│   ├── val/
│   │   ├── image3.png
│   │   ├── image4.png
│   │   └── ...
├── labels/
│   ├── train/
│   │   ├── image1.txt
│   │   ├── image2.txt
│   │   └── ...
│   ├── val/
│   │   ├── image3.txt
│   │   ├── image4.txt
│   │   └── ...
└── data.yaml
```



## Code
### 1. Preprocessing
- Make_label_text: 어떤 Object도 없는 이미지에 대해 비어있는 Label text(.txt) 파일 생성
- Make_yaml: Yolo model에 필요한 data.yaml 파일 생성
- 이미지의 밝기 및 대비를 조절
  - 전처리된 이미지는 images 폴더를 생성해 저장

### 2. Model training
- 사전학습 모델로 yolo11n (= yolo 11 nano) 모델을 사용
- 내가 보유한 데이터로 Fine-tuning 후 모델 저장

### 3. Prediction
- Yolo Fine-tuning 모델을 통해 Image Detection 수행
- (Option) EasyOCR을 활용한 텍스트 확인
