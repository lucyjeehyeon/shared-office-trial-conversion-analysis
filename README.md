# 유입에서 수익화까지, 무료체험 전환 체계 진단

> 공유오피스 3일 무료체험 고객의 신청·방문·결제 행동을 분석하고,  
> 반복 방문과 지점별 병목을 기반으로 전환 전략을 제안한 팀 프로젝트입니다.

---

## Project Overview

| 구분 | 내용 |
|---|---|
| 프로젝트 유형 | 데이터 분석 팀 프로젝트 |
| 분석 대상 | 무료체험 신청자 9,624명, 방문자 6,026명 |
| 분석 범위 | 신청 → 방문 → 결제 전환, 고객 행동, 지점별 성과 |
| 분석 기간 | 2021.05 ~ 2024.01 |
| 주요 산출물 | 분석 노트북, 발표자료, Tableau 대시보드 |

무료체험 신청과 방문은 안정적으로 유지되고 있었지만, 결제 전환율은 특정 시점 이후 급격히 감소했습니다.

이에 다음 세 가지 질문을 중심으로 분석했습니다.

1. 결제 전환의 이상 신호는 언제, 어느 단계에서 발생했는가?
2. 결제 고객과 미결제 고객의 이용 행동은 어떻게 달랐는가?
3. 지점마다 유입·경험·전환 중 어느 단계에서 병목이 발생했는가?

---

## Key Findings 🔎

### 1. 병목은 방문이 아니라 결제 단계에서 발생했습니다

| 지표 | 변화 전 | 변화 후 |
|---|---:|---:|
| 전체 결제 전환율 | 39.6% | 25.8% |
| 체험 시작 → 방문 | 61.1% | 73.7% |
| 방문 → 결제 | 41.0% | 25.8% |

방문 전환율은 **12.6%p 개선**됐지만, 방문 이후 결제 전환율은 **15.2%p 감소**했습니다.

따라서 결제 전환 하락의 핵심 병목은 유입 부족이 아니라 **방문 이후 수익화 단계**에서 발생한 것으로 판단했습니다.

---

### 2. 긴 체류보다 반복 방문이 결제와 더 밀접했습니다

| 이용 행동 | 결제 전환율 |
|---|---:|
| 단일 지점 1일 이용 | 35.05% |
| 단일 지점 반복 방문 | 43.43% |

같은 지점만 이용했더라도 여러 날짜에 걸쳐 방문한 집단의 결제율이 **8.38%p 높았습니다.**

다지점 이용자는 원본 결제율이 높았지만, 방문일수와 행동량을 통제하자 다지점 효과는 크게 감소했습니다.

| 분석 단계 | 다지점 오즈비 |
|---|---:|
| 다지점 여부만 반영 | 1.276 |
| 방문일수 추가 | 1.066 |
| 전체 행동 변수 추가 | 1.039 |

결제 전환과 더 일관되게 연결된 행동은 지점 이동 자체가 아니라 **서로 다른 날짜까지 이어진 반복 방문**이었습니다.

---

### 3. 전환 신호는 D1 이후 강화됐습니다

| 모델 | 관측 정보 | PR-AUC |
|---|---|---:|
| M0 | 체험 시작 정보 | 0.3840 |
| M1 | D0 행동까지 | 0.3961 |
| M2 | D1 행동까지 | 0.4250 |
| M3 | D2 행동까지 | 0.4590 |

D0 행동만 추가했을 때보다 D1과 D2 행동이 추가됐을 때 성능 증가 폭이 크게 나타났습니다.

모델의 절대적인 예측 성능은 높지 않았지만, **전환을 구분하는 행동 신호가 D1 이후부터 강화됐다**는 점을 확인했습니다.

---

### 4. 지점은 순위가 아니라 병목 유형으로 진단했습니다

행동·결제 데이터에 지하철 유동인구, 주변 인프라, 지도·블로그 리뷰를 결합했습니다.

지점 전체를 우수·열위로 나누는 대신 다음 세 가지 병목으로 구분했습니다.

- **유입 포착 병목**: 입지 잠재력에 비해 실제 수요가 부족한 지점
- **경험 수익화 병목**: 수요와 공간 경험에 비해 결제 전환이 낮은 지점
- **시간대 불일치 병목**: 상권 유동 패턴과 체험 수요가 맞지 않는 지점

이를 바탕으로 지점별로 수익화 투자, 유입 투자, 구조 재검토, 운영 표준화 전략을 제안했습니다.

---

## Strategy 🎯

### D1 재방문 유도

첫 방문 이후 두 번째 방문을 완료하지 않은 고객을 핵심 개입 대상으로 설정했습니다.

- 남은 체험 기간 안내
- 첫 이용 지점 재예약 링크 제공
- 두 번째 날짜 이용 완료 후 보상 제공
- 재방문 이후 상품 및 결제 CTA 노출

### 저녁 이용자 타기팅

18~23시 이용자의 결제 전환율은 **49.95%**로 가장 높았습니다.

이에 인근 직장인을 대상으로 한 저녁 체험권, 지역 제휴, 시간대별 상품 메시지를 제안했습니다.

### 결제 후 락인

다지점 혜택은 무료체험 단계보다 결제 이후의 유지 단계에 배치했습니다.

- Evening Work Bundle
- Local Business Bundle
- Portable Worker Bundle

체험 단계에서는 **다시 방문하도록**, 결제 이후에는 **어느 지점에서든 계속 이용하도록** 설계했습니다.

---

## A/B Test Proposal

D1 재방문 리마인드 메시지의 효과를 검증하는 실험을 설계했습니다.

| 항목 | 내용 |
|---|---|
| 실험 대상 | 첫 방문 후 재방문과 결제가 없는 사용자 |
| 대조군 | 기존 무료체험 안내 유지 |
| 실험군 | 남은 기간 안내 + 재방문 메시지 + 예약 링크 |
| 트래픽 분배 | 50:50 |
| 실험 기간 | 2주 |
| 1차 지표 | D2 종료 전 두 번째 날짜 방문 완료율 |
| 2차 지표 | 체험 종료 후 최종 결제 전환율 |
| 가드레일 지표 | 문의·불만률, 메시지 수신 거부율 |

---

## Dashboard

지점별 방문·결제·재방문 성과를 탐색할 수 있는 Tableau 대시보드를 제작했습니다.

[Tableau Public 대시보드 바로가기](https://public.tableau.com/app/profile/.79502505/viz/_17854259361800/2)

주요 구성은 다음과 같습니다.

- 방문자, 결제자, 결제 전환율, 재방문율
- 기간별 방문자 추이
- 방문자와 결제자 비교
- 지점별 방문자 분포
- 체험 이용 지속 퍼널
- 지점별 리뷰 현황

---

## Deliverables

| 산출물 | 링크 |
|---|---|
| 분석 노트북 | [Notebook](notebooks/shared_office_trial_analysis.ipynb) |
| 최종 발표자료 | [Presentation PDF](presentation/shared_office_trial_conversion_presentation.pdf) |
| 대시보드 소개 | [Dashboard README](dashboard/README.md) |
| Tableau Public | [Dashboard](https://public.tableau.com/app/profile/.79502505/viz/_17854259361800/2) |

---

## Tech Stack

### Data Analysis & Modeling

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white">
  <img src="https://img.shields.io/badge/Statsmodels-4051B5?style=flat-square">
  <img src="https://img.shields.io/badge/Scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white">
</p>

### Machine Learning

<p>
  <img src="https://img.shields.io/badge/XGBoost-EB5B28?style=flat-square">
  <img src="https://img.shields.io/badge/LightGBM-02569B?style=flat-square">
  <img src="https://img.shields.io/badge/PCA-4B8BBE?style=flat-square">
  <img src="https://img.shields.io/badge/KMeans-6A5ACD?style=flat-square">
  <img src="https://img.shields.io/badge/SHAP-FF6F00?style=flat-square">
</p>

### Visualization & Collaboration

<p>
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square">
  <img src="https://img.shields.io/badge/Seaborn-4C72B0?style=flat-square">
  <img src="https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white">
  <img src="https://img.shields.io/badge/Tableau-E97627?style=flat-square&logo=tableau&logoColor=white">
  <img src="https://img.shields.io/badge/Figma-F24E1E?style=flat-square&logo=figma&logoColor=white">
  <img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white">
</p>

---

## Team

김도영 · 김유림 · 김형준 · 이지현 · 임유주 · 정용택

데이터 전처리, 분석 방향 설정, 결과 검증, 전략 도출 및 발표자료 제작은 팀원 간 협업을 통해 진행했습니다.

---

> 기업명과 실제 지점명은 익명화했습니다.  
> 원본 데이터와 위치 정보가 포함된 Tableau 원본 파일은 공개 저장소에 포함하지 않았습니다.
