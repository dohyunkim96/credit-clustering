# 🔍 고객 세분화를 통한 수익 모델 최적화 방안 제안

## ✏️ 주요 분석 내용

- 고객 세분화를 위한 EDA (성별, 소득, 시간대, 업종별 소비 분석)
- 변수 선택 및 파생 변수 생성 (신용/소득/소비 지표)
- UMAP + KMeans를 통한 고객 클러스터링 수행
- 클러스터별 소비 특성 및 마케팅 전략 도출
- 군집별 ROI 기반 수익 기여율 분석

## 📊 기술 스택

- Python (Pandas, NumPy, Scikit-learn, UMAP)
- 시각화: Matplotlib, Seaborn
- 클러스터링: KMeans, DBSCAN (실험), UMAP
- 문서화: Word → PDF 보고서 첨부

## 🧑‍🤝‍🧑 팀 프로젝트 정보

- **참여 인원**: 총 5명
- **내 주요 역할**
  - EDA 및 변수 파생, 군집 시각화
  - UMAP + KMeans 클러스터링 수행
  - 클러스터별 수익 분석 및 마케팅 전략 도출
  - Word 보고서 최종 작성 및 시각 자료 정리

---

## 📁 폴더 구조

```
customer-segmentation-profit-optimization/
├── data/                  # 샘플 데이터 (실제 데이터는 비공개)
├── images/                # 보고서에 실제 사용된 핵심 그래프(주요 그래프)
├── experiments/           # 탐색적 분석 및 시도된 보조 시각화(보조 그래프)
├── notebooks/             # 분석 노트북 (EDA, Clustering 등)
├── report/                # 최종 결과보고서 (PDF)
├── requirements.txt       # 사용한 라이브러리 목록
├── .gitignore             # Git 무시 설정
└── README.md              # 프로젝트 설명 파일
```

---

## 📎 클러스터링 대표 시각화

![변수 중요도](images/feature_importance.png)  
![UMAP 클러스터링](images/umap_kmeans.png)  
![히트맵](images/cluster_heatmap.png)  
![ROI 및 수익 기여액](images/cluster_roi.png)
