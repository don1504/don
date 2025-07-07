# 📘 OpenCV 정리 문서

## 1. OpenCV란?

OpenCV(Open Source Computer Vision Library)는 실시간 컴퓨터 비전 및 이미지 처리에 활용되는 **오픈소스 라이브러리**입니다. 

- 2000년 인텔(Intel) 주도로 개발
- 이미지 및 비디오 처리, 객체 검출, 얼굴 인식, 딥러닝 모델 추론 등에 사용
- Python, C++, Java 등 다양한 언어 지원
- 빠르고 효율적인 처리 성능으로 산업, 연구, 로봇 등 다양한 분야에 활용

---

## 2. OpenCV 사용을 위한 주요 라이브러리

| 라이브러리 이름 | 설명 |
|----------------|------|
| `opencv-python` | OpenCV의 기본 이미지/영상 처리 기능을 포함한 패키지 |
| `opencv-contrib-python` | 추가적인 알고리즘(SIFT, SURF 등)이 포함된 확장 패키지 |
| `numpy` | OpenCV의 이미지 데이터 처리를 위한 필수 수치 계산 라이브러리 |
| `matplotlib` | 이미지 출력 및 디버깅용 시각화 라이브러리 |
| `imutils` | 이미지 회전, 크기 조절 등 자주 쓰는 기능 모음 (보조용) |

🔧 설치 예시:

```bash
pip install opencv-python
pip install numpy
pip install matplotlib
pip install imutils
```

---

## 3. OpenCV 주요 용어 정리

| 용어 | 설명 |
|------|------|
| BGR / RGB | OpenCV는 기본적으로 BGR 순서를 사용 |
| Grayscale | 흑백 이미지. 색상이 아닌 밝기 정보만 저장 |
| ROI (Region of Interest) | 관심 영역. 이미지 내 특정 부분을 의미 |
| Thresholding | 이미지 이진화 처리 기법 (ex. 흑/백 구분) |
| Canny Edge | 윤곽선(엣지) 검출 알고리즘 |
| Cascade Classifier | 얼굴, 눈 등의 객체 검출 알고리즘 |
| Contour | 객체의 외곽 경계를 추출한 선 |
| Morphological Transform | 침식, 팽창 등 형태학적 이미지 처리 |
| DNN (Deep Neural Network) | OpenCV에 내장된 딥러닝 추론 엔진 |
| Haar Cascade | 사전 학습된 얼굴 검출 모델 (XML 포맷) |

---

📎 더 알아보기:
- 공식 문서: [https://docs.opencv.org](https://docs.opencv.org)
- GitHub 저장소: [https://github.com/opencv/opencv](https://github.com/opencv/opencv)
