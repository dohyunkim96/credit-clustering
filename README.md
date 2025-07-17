# 🔍 고객 세분화를 통한 수익 모델 최적화 방안 제안

## ✏️ 주요 분석 내용

- 고객 세분화를 위한 EDA (성별, 소득, 시간대, 업종별 소비 분석)
- 변수 선택 및 파생 변수 생성 (신용/소득/소비 지표)
- UMAP + KMeans를 통한 고객 클러스터링 수행
- 클러스터별 소비 특성 및 마케팅 전략 도출
- 군집별 ROI 기반 수익 기여율 분석

## 🧪 가설 기반 EDA 요약

EDA 과정에서는 다음과 같은 가설을 검토하고, 실제 데이터 분석을 통해 일부 가설을 채택하여 인사이트를 도출하였습니다.

- 고객의 **거주지에 따른 소비 패턴 차이**를 확인해 지역별 마케팅 전략 수립 가능성을 제시  
- **고소득층**은 **1인당 소비 규모**가 높으며 프리미엄 상품 대상군으로 유효함  
- **소득 수준이 높을수록 소비 카테고리 다양성**이 증가하는 경향 확인  
- **50~60대 연령층의 소비력**이 높아 프리미엄 마케팅 타겟으로 적합  
- **온라인 거래 집중 시간대**를 기반으로 시간대별 프로모션 전략 수립 가능성 탐색

> ※ 해당 가설들은 텍스트 기반 분석으로만 요약되었으며, 시각화 그래프는 report에 포함되어 있습니다.

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
