# 2023_summer An-Initial-Study-of-Deep-Learning-Architecture-for-Image-Recognition
### This repository summarizes the overall study of Deep Learning Architecture
### in the 2023-Summer Vacation Image Recognition field.
##### 여러 인공지능 분야 중, Computer Vision 영역 기초 탐구를 바탕으로 파이토치를 활용해
##### 최신 영상인식을 위한 딥러닝 논문 재현 및 survey를 진행했습니다.
##### On CIFAR100 dataset, achieves top-1 accuracy > 80% within 3 hour.
##### On CIFAR100 dataset, achieves top-1 accuracy > 82% within 2 train hour
##### On CIFAR100 dataset, achieves top-1 acacuracy > 82% using timm library‘s various augmentation techniques. can only use the given model(ResNet-50)
##### 등 CIFAR100 dataset에 대해 제한된 train time 안에서 accuracy를 높이는 작업을 수행했습니다.
##### 향후 최신 trend 기술 Vision Transformer (ViT) 에 대한 학습 및 이해를 가졌습니다.
## 1.1. Patch Embedding 뜯어 보기

### Patch Embedding Layer 개념

2D 인풋 이미지에서 `p x p` 크기의 이미지를 `1D` 토큰으로 만드는 레이어

![image](https://user-images.githubusercontent.com/31476895/219355588-5297a74a-eb7e-4548-a0c2-e561062d975a.png)

### Patch Embedding Layer 구현

함수 실행 순서: `2D convolution` -> `Flatten` -> `Transpose`

![image](https://user-images.githubusercontent.com/31476895/219355004-33ec948f-f14e-4a4f-a8a0-6767f2959131.png)
## 1.2. Attention 뜯어보기

### Transformer Encoder 와 Multi-headed self attention 개념

- `A = Q x K.t()`: Query `Q` 와 Key `K` 를 이용해서 Attention map `A` 을 구함.
- `MHSA(x) A x V`: Attention value `A` 와 Valeu `V` 를 이용해서 최종 아웃풋을 구함.
- 생략한 부분: softmax, output project layer, multi-head

![image](https://user-images.githubusercontent.com/31476895/219355470-803208ac-82fc-4343-a04e-5c400dee2524.png)
## 2.1. ViT 모델 구조

- Model: ViT-B/16
- Top 1: 84.268 (%)
- Top 5: 96.802 (%)
- Parameter: 86.54 (M)
- Image size: 224 x 224 (px)
- Crop percent: 0.875 (%)
- Interpolation: bilinear

## 3.1. Hybrid 모델 구조

- Model: ViT-B/16+R50
- Top 1: 84.972
- Top 5: 97.288
- Parameter: 98.95
- Image size: 384
- Crop percent: 1.0
- Interpolation: bicubic

##### 마지막 2주간은 Analysis 학습을 진행하며 실험과 연구를 효율적이고 신뢰성 있게 설득하기 위해 성능 향상 근거나 논리적인 설명이 필요하고
##### 사업이나 의료계의 경우 소비자나 환자들에게 설명을 위해서 어떤 근거에 의해 결론이 도출되었는지 명확한 이유가 필요하기 때문에
##### DeepLift, GradCAM, Self Attention Heatmap, Effective Receptive Field, PCA,
##### Robustness, Consistency, Frequency, and ShapeTexture와 같은 다양한 Analysis framework를 학습했습니다.
###### ⭐Let's have a better day today than yesterday⭐
