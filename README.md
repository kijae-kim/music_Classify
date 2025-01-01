# music_Classify
음악장르분류기_handcrafted feature를 활용하여

---

# 🎵 음악 장르 분류기

## 📌 소개
이 프로젝트는 [Kaggle 대회](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification))에서 영감을 받아 제작된 **음악 장르 분류 시스템**입니다. 오디오 데이터의 특징을 활용하여 다양한 음악 장르를 분류하며, 오디오 데이터 처리와 머신러닝 모델 학습 및 평가를 탐구하는 데 중점을 두었습니다.

## 🚀 주요 기능
- **오디오 특징 추출**: Librosa 또는 Essentia 라이브러리를 사용해 MFCC, 크로마(chroma), 스펙트럼 대비(spectral contrast) 등 주요 오디오 특징을 추출합니다.
- **다중 클래스 분류**: 여러 장르를 높은 정확도로 예측할 수 있는 분류기를 학습합니다.
- **데이터 시각화**: 데이터 분포 및 모델 성능을 시각화 도구(예: Matplotlib, Seaborn)를 통해 확인합니다.
- **확장 가능한 파이프라인**: 다른 알고리즘이나 특징으로 실험하기 쉽도록 설계된 유연한 파이프라인을 제공합니다.

## 📂 프로젝트 구조
```
📁 music-genre-classifier
├── 📁 data/            # 학습 및 테스트에 사용된 데이터셋
├── 📁 notebooks/       # 데이터 탐색 및 실험용 Jupyter 노트북
├── 📁 models/          # 학습된 모델 및 로그
├── 📁 src/             # 소스 코드
│   ├── preprocess.py   # 오디오 데이터 전처리
│   ├── features.py     # 특징 추출 함수
│   ├── train.py        # 모델 학습 및 평가
│   └── predict.py      # 예측 파이프라인
├── 📄 requirements.txt # 프로젝트 종속성
└── 📄 README.md        # 프로젝트 문서
```

## 📊 데이터셋
이 프로젝트는 Kaggle에서 제공된 오디오 데이터를 사용했으며, 여러 장르(예: 팝, 클래식, 재즈 등)로 라벨링되어 있습니다. 주요 전처리 과정은 다음과 같습니다:
1. 오디오를 모노(mono) 형식으로 변환하고 샘플링 속도를 표준화.
2. 시간 영역 및 주파수 영역에서 특징을 추출.

## 🔍 주요 기법
1. **특징 추출**:
   - MFCC
   - 크로마(Chroma) 특징
   - 제로 크로싱 비율(Zero-crossing rate)
   - 스펙트럼 중심(Spectral centroid)

2. **모델링**:
   - 기본 모델: 로지스틱 회귀(Logistic Regression), 랜덤 포레스트(Random Forest)
   - 고급 모델: 스펙트로그램 기반 CNN(Convolutional Neural Networks)
   - 하이퍼파라미터 튜닝: GridSearchCV 또는 Optuna 사용

3. **평가**:
   - 사용 지표: 정확도(Accuracy), F1 스코어, 혼동 행렬
   - 시각화: 혼동 행렬 히트맵, 장르별 정밀도-재현율 곡선

## 🛠️ 설치 및 실행
1. 레포지토리 클론:
   ```bash
   git clone https://github.com/yourusername/music-genre-classifier.git
   cd music-genre-classifier
   ```
2. 종속성 설치:
   ```bash
   pip install -r requirements.txt
   ```
3. 프로젝트 실행:
   - 전처리:
     ```bash
     python src/preprocess.py
     ```
   - 모델 학습:
     ```bash
     python src/train.py
     ```
   - 장르 예측:
     ```bash
     python src/predict.py --input test_audio.mp3
     ```

## 📈 결과
- **최고 모델 정확도**: 테스트 데이터에서 92%
- **혼동 행렬**:
  
  <img width="577" alt="스크린샷 2025-01-01 오후 4 43 20" src="https://github.com/user-attachments/assets/0250266f-ee54-4ea3-b2ca-deacd6aca0d1" />

  
- **장르별 F1 점수**:
  
  <img width="571" alt="스크린샷 2025-01-01 오후 4 45 29" src="https://github.com/user-attachments/assets/e02924c2-15b8-48a1-8a68-cf144026df9c" />


## 💡 향후 작업
- RNN 또는 Transformer와 같은 시계열 데이터를 처리할 수 있는 고급 모델 탐색
- 일반화를 향상시키기 위한 더 크고 다양한 데이터셋 사용
- 사용자 친화적인 인터페이스를 통한 실시간 장르 예측 기능 추가



---

추가로 강조하고 싶은 점이나 수정이 필요한 내용이 있다면 알려주세요! 😊
