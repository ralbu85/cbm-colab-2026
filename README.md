# CBM 데이터 분석 실습 (Colab)

설비가 고장 나기 전에 **상태를 보고 정비하는 것**(상태기반정비, CBM)의 핵심 알고리즘을 실제 데이터로 직접 계산해 봅니다.

```
센서·기록 데이터 → 특징(건전성 지표) → ① 이상탐지 → ② 고장진단 → ③ 잔여수명(RUL) 예측 → 정비 결정
```

## 시작하는 법

1. 아래 표에서 **Colab에서 열기** 배지를 누릅니다. (구글 계정 로그인)
2. 메뉴 **파일 → Drive에 사본 저장**을 누릅니다. 사본을 저장하지 않으면 내가 쓴 코드가 사라집니다.
3. 맨 위 **준비 셀**부터 순서대로 `Shift + Enter`로 실행합니다. 준비 셀이 실습 데이터와 한글 글꼴을 자동으로 내려받습니다.
4. 창을 오래 두어 런타임이 초기화되면, **준비 셀부터 다시** 실행하세요.

설치할 것은 없습니다. 인터넷 브라우저와 구글 계정만 있으면 됩니다.

| 표시 | 뜻 |
|---|---|
| ▶ | 제공 코드 — 그대로 실행하고 결과를 읽습니다 |
| ✍️ | 직접 입력 — 보여 준 코드를 **손으로 타이핑**합니다 (반복되는 핵심 패턴) |
| 📝 | 과제 — 앞의 코드를 바꿔 스스로 풉니다 |
| 💬 · ✅ | 결과 해설 · 체크포인트 |

## 노트북

| 순서 | 내용 | 시간 | 열기 |
|---|---|---|---|
| 00 | 시작하기 — Colab 사용법과 분석의 5가지 핵심 패턴 | 30분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/00_%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0_Colab%EA%B3%BC_%ED%95%B5%EC%8B%AC%ED%8C%A8%ED%84%B4.ipynb) |
| 1-1 | 하드디스크 6만 대의 고장 기록과 고장률 | 70분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/1-1_%EA%B3%A0%EC%9E%A5%EA%B8%B0%EB%A1%9D%EA%B3%BC_%EA%B3%A0%EC%9E%A5%EB%A5%A0.ipynb) |
| 1-2 | SMART 신호로 고장을 미리 알 수 있을까? | 80분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/1-2_SMART%EA%B2%BD%EB%B3%B4_%EA%B7%9C%EC%B9%99%EA%B3%BC%EC%84%B1%EB%8A%A5.ipynb) |
| 1-3 | 경보 기준을 비용으로 정하기 | 60분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/1-3_%EA%B2%BD%EB%B3%B4%EA%B8%B0%EC%A4%80%EA%B3%BC_%EC%A0%95%EB%B9%84%EB%B9%84%EC%9A%A9.ipynb) |
| 2-1 | 유압 장치 데이터 파악하기, 그리고 좋은 특징 고르기 | 80분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/2-1_%EC%84%BC%EC%84%9C%EC%8B%A0%ED%98%B8%EC%99%80_%ED%8A%B9%EC%A7%95%EC%B6%94%EC%B6%9C.ipynb) |
| 2-2 | 이상탐지 — 정상 데이터만으로 경보 만들기 | 100분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/2-2_%EC%9D%B4%EC%83%81%ED%83%90%EC%A7%80_%EC%A0%95%EC%83%81%EC%9D%84%EB%B0%B0%EC%9A%B0%EA%B3%A0_%EB%B2%97%EC%96%B4%EB%82%A8%EC%B0%BE%EA%B8%B0.ipynb) |
| 2-3 | 고장진단 — 어느 부품이 얼마나 나빠졌나 | 100분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/2-3_%EA%B3%A0%EC%9E%A5%EC%A7%84%EB%8B%A8_%EB%B6%84%EB%A5%98%EB%AA%A8%EB%8D%B8.ipynb) |
| 2-4 | 판정 기준을 비용으로 정하기 — 심한 누설을 놓치지 않으려면 | 80분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/2-4_%ED%8C%90%EC%A0%95%EA%B8%B0%EC%A4%80%EC%9D%84_%EB%B9%84%EC%9A%A9%EC%9C%BC%EB%A1%9C_%EC%A0%95%ED%95%98%EA%B8%B0.ipynb) |
| 3-1 | 필터가 막혀 가는 과정 — 열화 데이터와 건전성 지표 | 80분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/3-1_%EC%97%B4%ED%99%94%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%99%80_%EA%B1%B4%EC%A0%84%EC%84%B1%EC%A7%80%ED%91%9C.ipynb) |
| 3-2 | RUL 예측 ① — 추세를 연장해 고장선에 닿는 시간 구하기 | 80분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/3-2_RUL%EC%98%88%EC%B8%A11_%EC%B6%94%EC%84%B8%EC%99%B8%EC%82%BD.ipynb) |
| 3-3 | RUL 예측 ② — 과거 고장 이력에서 머신러닝으로 배우기 | 100분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/3-3_RUL%EC%98%88%EC%B8%A12_%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D%ED%9A%8C%EA%B7%80.ipynb) |
| 3-4 | 언제 교체할까? — 시간 기준 vs 상태 기준 vs 예측 기준 | 100분 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/3-4_RUL%EB%A1%9C_%EA%B5%90%EC%B2%B4%EC%8B%9C%EC%A0%90_%EA%B2%B0%EC%A0%95%ED%95%98%EA%B8%B0.ipynb) |
| 3-5 | [선택 심화] 시계열 기초모델(PatchTST)로 미래 전류를 예측해 RUL 구하기 | 40~60분 · 선택 | [![Colab에서 열기](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ralbu85/cbm-colab-2026/blob/main/notebooks/3-5_%EC%84%A0%ED%83%9D%EC%8B%AC%ED%99%94_%EC%8B%9C%EA%B3%84%EC%97%B4%EA%B8%B0%EC%B4%88%EB%AA%A8%EB%8D%B8.ipynb) |

## 데이터 출처

| 데이터 | 출처 | 라이선스 |
|---|---|---|
| 하드디스크 SMART 기록 (2026년 1분기, 60,000대 표본) | [Backblaze Hard Drive Data](https://www.backblaze.com/cloud-storage/resources/hard-drive-test-data) | 무료 이용 · 출처 표시 · 판매 금지 (Backblaze 이용 조건) |
| 유압 시험장치 상태 감시 | Helwig, Pignanelli, Schütze (2015), [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/447/condition+monitoring+of+hydraulic+systems), DOI 10.24432/C5CW21 | CC BY 4.0 |
| 압출기 필터 막힘 RUL 실험 | Ferreira, Ko, Li, Otto, *The University of Melbourne – Extrusion Filter RUL Dataset*, [Zenodo](https://zenodo.org/records/20710452), [데이터 논문](https://doi.org/10.1016/j.dib.2026.113254) | CC BY 4.0 |
| 나눔고딕 글꼴 | NAVER | SIL OFL 1.1 (`fonts/OFL.txt`) |

수업용으로 가공했습니다: 유압 데이터는 사이클별 특징을 계산하고 학습/평가를 상태 조합 단위로 나눴습니다. 필터 데이터는 10초 평균 창으로 정리하고 분석 대상 41회를 학습 33회 / 평가 8회로 나눴습니다. 선택 심화(3-5)의 저장된 예측은 [IBM Granite PatchTST-FM r2](https://huggingface.co/ibm-granite/granite-timeseries-patchtst-fm-r2)의 실제 출력입니다.
