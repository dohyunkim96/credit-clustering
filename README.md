# 🔍 고객 세분화를 통한 수익 모델 최적화 방안 제안

## 📝 개요  
본 프로젝트는 카드사 고객의 거래 데이터를 분석하여 **소비 패턴 기반의 고객 세분화(Clustering)** 를 수행하고, 각 군집별로 **맞춤형 마케팅 전략**을 수립하여 **카드사 수익률 향상**을 도모하는 것을 목표로 합니다. 특히 소비 성향, 부채 규모, 신용 등급 등의 금융 지표를 중심으로 **5개 고객 군집**을 도출하고, 군집별 ROI 기반 마케팅 방안을 제시하였습니다.

## 📌 주요 결과 요약  
- UMAP + KMeans 기반 고객 세분화를 통해 5개 클러스터 도출  
- 각 군집별 특성과 신용/소득/소비 특성의 차이를 반영한 전략 수립  
- ‘초고위험 부채 집중군’에 대한 리스크 관리 전략 및 ‘프리미엄 안정 고객군’에 대한 고급 마케팅 전략 설계  
- 마케팅 실행 시 수익 증가 기대액 **$95,207**, ROI 최대 **+62.9%**, 전체 수익률 **+9.8%p 향상**

## 💰 수익 분석 요약

군집별 맞춤 마케팅 전략 적용 시 다음과 같은 수익 향상 효과를 확인하였습니다.

- 📈 총 기대 수익 증가액: **$95,207**
- 📊 전체 수익 기준 수익률 향상: **+9.8%**
- 💸 최고 ROI 군집: `밸런스 소비 중심군` (**+62.9%**)
- 💥 핵심 수익 기여군: `다이내믹 리스크하이퍼 군` (**$50,972** 증가)

> ✅ ROI와 수익 증가액을 기준으로 최적의 타겟 마케팅 우선순위를 제안

## 📁 데이터 소개  
- 출처: [Kaggle 카드 거래 데이터셋](https://www.kaggle.com/datasets/computingvictor/transactions-fraud-datasets/data)
- 구성: 고객 정보 (2,000명), 거래 데이터 (1,300만 건), 카드 정보 (6,146건), 업종 정보 (MCC 코드)

<table>
<tr>
<td valign="top">

<h4>주요 변수 설명</h4>

<table>
<thead>
<tr><th>변수명</th><th>의미</th></tr>
</thead>
<tbody>
<tr><td><code>tx_amount</code></td><td>총 거래 금액 (연간 기준)</td></tr>
<tr><td><code>tx_count</code></td><td>총 거래 건수</td></tr>
<tr><td><code>per_capita_income</code></td><td>1인당 연간 소득</td></tr>
<tr><td><code>total_debt</code></td><td>총 부채 금액</td></tr>
<tr><td><code>credit_score</code></td><td>신용 점수 (0~850 범위)</td></tr>
<tr><td><code>online_tx_ratio</code></td><td>온라인 거래 비중 (%)</td></tr>
<tr><td><code>credit_risk</code></td><td>부채 대비 신용 위험도</td></tr>
<tr><td><code>lifetime</code></td><td>가입 기간 (월 기준)</td></tr>
</tbody>
</table>

</td>
<td width="5%"></td> <!-- 간격 -->

<td valign="top">

<h4>파생 변수 설명</h4>

<table>
<thead>
<tr><th>변수명</th><th>의미</th></tr>
</thead>
<tbody>
<tr><td><code>income_to_debt_ratio</code></td><td>연소득 대비 부채 비율</td></tr>
<tr><td><code>credit_to_tx_ratio</code></td><td>거래금액 대비 신용점수 비율</td></tr>
<tr><td><code>debt_to_credit_ratio</code></td><td>신용 대비 부채 비율</td></tr>
</tbody>
</table>

</td>
</tr>
</table>

## 🧪 가설 기반 EDA 요약
- 고객의 **거주지에 따른 소비 패턴 차이**를 확인해 지역별 마케팅 전략 수립 가능성을 제시  
- **고소득층**은 **1인당 소비 규모**가 높으며 프리미엄 상품 대상군으로 유효함  
- **소득 수준이 높을수록 소비 카테고리 다양성**이 증가하는 경향 확인  
- **50~60대 연령층의 소비력**이 높아 프리미엄 마케팅 타겟으로 적합  
- **온라인 거래 집중 시간대**를 기반으로 시간대별 프로모션 전략 수립 가능성 탐색  

> ※ 해당 가설들은 텍스트 기반 분석으로만 요약되었으며, 시각화 그래프는 report에 포함되어 있습니다.

## 🛠 기술 스택  
- Python (pandas, numpy, sklearn, umap-learn, seaborn, matplotlib)  
- GeoPandas (위경도 기반 지역군 분석)  
- SQL (대용량 거래데이터 전처리 및 집계)

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

## 🧭 클러스터별 군집명 정리

| 군집 번호 | 군집명 (별칭)             | 주요 특징 요약                          |
|----------|--------------------------|----------------------------------------|
| 군집 0   | 다이내믹 리스크 하이퍼군   | 고소득·고소비·온라인 중심, 신용위험도 있음 |
| 군집 1   | 초고위험 부채 집중군       | 소득 대비 부채 압도적, 디지털 비활성         |
| 군집 2   | 프리미엄 안정 고객군       | 고소득·무부채·고신용, 거래금액도 안정적      |
| 군집 3   | 밸런스 소비 중심군         | 중간 소비력, 장기 충성 고객군, 고령층 비중 ↑  |
| 군집 4   | 저소비 유지관리군          | 소비·소득 모두 낮고, 보수적 소비 패턴        |

---

## 📎 클러스터링 대표 시각화

![UMAP 클러스터링](images/umap_kmeans.png)  
![변수 중요도](images/feature_importance.png)  
![히트맵](images/cluster_heatmap.png)  
![ROI 및 수익 기여액](images/cluster_roi.png)

---

## 📄 보고서 / 노트북 링크  
- 📘 [최종 보고서 PDF](./report/Project%20Report.pdf)  
- 📓 분석 코드: `notebooks/` 폴더 참고

---

## ⚙️ 실행 환경  
```bash
conda create -n segmentenv python=3.9
conda activate segmentenv
pip install -r requirements.txt
```

---

## 🚀 향후 개선 방향
- LTV/Churn 예측 모델 통합을 통한 정량 기반 마케팅 우선순위 정교화
- 클러스터 내 세부 분류(Subgrouping)를 통한 개인화 전략 설계
- 시간대·월별 소비 패턴 기반의 이상 탐지 및 마케팅 반응률 트래킹 고도화

---

## 👥 팀 정보 / 역할 분담
본 프로젝트는 5인 팀 프로젝트로 수행되었습니다.
| 이름  | 담당 역할                                         |
| --- | --------------------------------------------- |
| 김도현 | 데이터 전처리, 머신러닝 튜닝, EDA, 클러스터링, 마케팅 전략 도출, 보고서 작성 |
| 이영섭 | 시계열 분석, EDA, 클러스터링, 마케팅 전략 도출, 보고서 작성 |
| 이하린 | 기술 통계 분석, 시각화, EDA, 클러스터링, 마케팅 전략 도출, 보고서 작성 |
| 장다향 | 일정 관리, 역할 배정, 데이터 수집, EDA, 클러스터링, 마케팅 전략 도출, 보고서 작성 |
| 전재영 | 크로스탭 분석, EDA, 클러스터링, 마케팅 전략 도출, 보고서 작성, 발표 |
