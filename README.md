
---

# 🚴‍♀️ 서울시 공공자전거 이용률 증대 프로젝트

## 📌 프로젝트 개요
서울시 공공자전거 이용률을 증가시키기 위해 **목적지까지의 진행률(Bar)을 표시하는 기능**을 도입했을 때, 실제로 이용률에 어떤 영향을 미치는지 분석한 시뮬레이션 프로젝트입니다.

- **문제 정의**:  
  - 이용자가 현재 위치와 목적지 간 거리감을 느끼며 중도 포기하는 경우가 많음.  
  - 이를 해결하기 위해 **진행률 표시 기능**을 제안.

- **목표**:  
  - 진행률 표시 기능이 사용자 경험을 개선하고, 실제 이용률 증가로 이어지는지 평가.

- **사용 데이터**:  
  - 2024년 서울시 공공자전거 대여 데이터  
  - Google Place API + 기상청 API  

---

## 🛠️ 사용 기술 및 도구
- **데이터 수집**: API 활용 (Google Place API, 기상청 API)  
- **데이터 처리 및 분석**: SQL (BigQuery)  
- **실험 설계 및 검증**: A/B 테스트 (시뮬레이션)  
- **통계 분석**: 논리적 사고 및 Mann-Whitney U Test  

---

## 🔍 분석 과정
1. **주요 분석 내용**:
   - A/B 테스트 그룹(진행률 표시 여부)에 따라 이동거리 및 소요 시간 비교.
2. **가설 설정**:
   - 귀무가설(H0): 진행률 표시 여부는 이용률에 영향을 미치지 않는다.
   - 대립가설(H1): 진행률 표시 여부는 이용률에 영향을 미친다.
3. **통계적 방법**:
   - Mann-Whitney U Test를 통해 두 그룹 간 차이를 비교.

---

## 📊 실험 결과
- **p-value**: `5.679061e-26`  
  → 귀무가설(H0)을 기각. 즉, 진행률 표시 여부가 이용률에 영향을 미쳤음을 의미.
- **Cohen's d (효과 크기)**: `0.089161`  
  → 효과 크기가 작아 실제 변화는 미미할 가능성이 있음.

### ✅ 결론
진행률(Bar)을 보여준 그룹과 그렇지 않은 그룹 간 **유의미한 차이**가 존재했으나, 효과 크기가 작아 추가적인 개선이 필요합니다.

---

## 🛠️ 개선 방향
1. **추가 동기부여 요소 결합**:
   - 예: 보상 시스템(완주 시 할인 쿠폰 제공 등).
2. **세분화된 사용자 분석**:
   - 연령대, 자주 이용하는 사용자 vs 신규 사용자 등 그룹별로 세분화된 데이터 분석.
3. **추가 실험 설계**:
   - 다른 UI/UX 요소와 결합하여 최적의 사용자 경험 제공.

---

## 📈 결과 시각화
<image src = "https://i.imgur.com/g4TNG4V.png"/>

---
