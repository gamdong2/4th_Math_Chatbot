# 초등학교 4학년 수학 챗봇 개발 및 성능 평가
<img width="734" alt="초등 4학년 수학 검색 챗봇 개발 발표 자료" src="https://github.com/user-attachments/assets/1c414c57-b7eb-41fd-bbdc-975cfdb207c7">

## Skills
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white"/>&nbsp;
<img src="https://img.shields.io/badge/pandas-150458.svg?style=for-the-badge&logo=pandas&logoColor=white"/>&nbsp;
<img src="https://img.shields.io/badge/nltk-006600?style=for-the-badge&logo=nltk&logoColor=white"/>&nbsp;
<img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white"/>&nbsp;
<img src="https://img.shields.io/badge/sqlite3-003B57?style=for-the-badge&logo=sqlite&logoColor=white"/>&nbsp;

## 프로젝트 제목
**초등학교 4학년 수학 챗봇 개발 및 성능 평가**

## 프로젝트 상세

- **진행 기간**: 2024년 9월 12일 ~ 2024년 9월 23일
- **프로젝트 유형**: 팀 프로젝트

## 프로젝트 목표
- 초등학교 4학년 수학 교과 과정의 학습 내용을 기반으로, 학생들이 자기주도 학습을 할 수 있도록 돕는 챗봇 개발
- 사용자가 질문을 입력하면 해당 질문에 대해 연관된 수학 강의를 추천(강의 썸네일, 요약, 키워드 제공)

## 사용한 데이터 셋
- **데이터**: 초등학교 4학년 강의 영상 (→ 음성 → 텍스트 → 요약 및 키워드 추출)

## 워크플로우

1. **패키지 임포트**
   - 주요 패키지: pandas, scikit-learn, Django, SQLite, NLTK 등의 NLP 패키지

2. **데이터 로드 및 요약**
   - 데이터 로드 후 기본 정보와 결측치를 확인하여 전처리 준비

3. **데이터 전처리**
   - 강의 내용에서 주요 질문 키워드를 추출하고 학생 질문을 전처리
   - 텍스트 정규화 및 불용어 제거를 통해 자연어 처리 과정 최적화

4. **챗봇 응답 함수 설정**
   - Django의 비동기 기능을 활용하여 사용자 질문에 대한 응답 시간을 단축
   - 질문 키워드를 추출하여 관련 강의를 검색하고 응답 생성

5. **성능 평가 및 분석**
   - 챗봇 성능 테스트 코드(chatbot_performance_test.py)를 사용하여 정확도, 정밀도, 재현율, F1 점수 및 평균 응답 시간을 평가하여 분석

## 프로젝트 결과

### 구현 기능
- 학생의 질문에 실시간으로 응답하여 학습을 지원하는 챗봇
- Django ORM을 통해 DB에서 강의 데이터를 검색하고 학습에 필요한 자료를 제공
- 챗봇 성능 테스트를 통해 정확도, 정밀도, 재현율, F1 점수 및 응답 시간을 분석

## 트러블 슈팅

- **오류**: `AttributeError: 'NoneType' object has no attribute 'split'`
  - **상황**: CSV 파일에서 데이터를 로드하여 데이터베이스에 삽입하는 과정에서 특정 열의 데이터가 누락됨
  - **해결 방법**: `None` 체크를 통해 데이터가 비어있는지 확인하고, 비어 있을 경우 기본 값을 할당하거나 해당 데이터를 건너뛰도록 처리
  
- **오류**: `OperationalError: no such table: Lecture`
  - **상황**: 모델이 정의된 후 마이그레이션을 적용하지 않아 테이블이 생성되지 않음
  - **해결 방법**: `python manage.py makemigrations`와 `python manage.py migrate` 명령어를 사용하여 모델에 맞는 테이블을 생성하여 해결

## 프로젝트를 통해 얻은 역량

- Django와 OpenAI API를 활용한 챗봇 개발 및 성능 최적화
- 데이터 전처리와 텍스트 요약을 통해 DB 생성 및 관리
- 챗봇 성능(정확도, 정밀도, 재현율, F1 점수 및 평균 응답 시간) 평가
