# 경희대학교 2020-1학기 데이터분석캡스톤디자인

## 주제: 스미싱 문자를 판독해주는 챗봇
20-1학기 데이터분석캡스톤디자인
<br>

### 스미싱 문자 데이터 출처: 데이콘 금융 문자 분석 경진대회 https://dacon.io/competitions/official/235401/overview/
### 데이콘, 스폰서의 협의로 인해 대회 종료 후 데이터 다운로드 불가능합니다. 
### 따라서 repository에서도 제공받은 데이터를 공개하지 않을 것입니다.

<br>
### 추진일정 [간략]
|순 번|추진 내용|4월|5월|6월|비고
|:----|:-----:|:-----:|:-----:|:-----:|:-----:|
|1|개발환경 구축(Colab을 이용한 Mecab형태소 분석 패키지 설정)|1주|||완료|
|2|탐색적 데이터 분석(EDA)|2주|||완료|
|3|불용어(비식별화된 정보, 한국어 조사, 공통적으로 많이 쓰인 단어) 제거|3주|||완료|
|4|모델학습을 위해 텍스트 데이터를 시퀀스 데이터로 변환해줌(Keras Tokenizer 이용)|3주|||sklearn Tfidfvectorizer 이용|
|5|층화추출 (class label 94%:6%로 불균형), 변수 선택 |4주|||완료|
|6|LightGBM, SupportVectorMachine 모델 구축 및 검증||1주||완료|
|7|하이퍼 파라미터 선택||1주||완료|
|8|LSTM 모델 구축 및 검증||2주||LGBM, SVM 성능이 우수함 -> 생략|
|9|하이퍼 파라미터 선택||2주||LGBM, SVM 성능이 우수함 -> 생략|
|10|LightGBM과 LSTM 모델 중 정확도, 속도를 고려하여 더 우수한 모델 선택||2주||SVM(속도, F-measure) 모두 우수|
|11|LIME 학습 및 모델 적용||3주||완료|
|12|카카오톡·라인 플러스 친구, 웹사이트 중 이번 모델에 적합한 플랫폼 선정||4주||카카오톡·라인 모두 고려 중|
|13|8)의 a에 의해 선정된 플랫폼 학습||4주||진행 중|
|14|웹 서비스 개발|||1, 2주|진행 중|
|15|웹서비스 배포|||2, 3주|진행 예정|

-------------


<br>
<br>
### 추진일정(안) [상세]
   1) 4월 3일 ~ 4월 9일
   : 개발환경 구축(Colab을 이용한 Mecab 설치) 및 관련 연구 조사, 문자메시지 형태소 분류
 
   2) 4월 10일 ~ 4월 16일
   : 탐색적 데이터 분석(EDA) 
     a. Positive, Negative data 비율 확인
     b. Bag of Words를 이용한 DTM 분석, TF-IDF 분석 -> 스미싱, 일반 문자의 내용 분석    

   3) 4월 17일 ~ 4월 23일
    a. 4월 17일 ~ 4월 20일.
    : 불용어(비식별화된 정보, 한국어 조사, 공통적으로 많이 쓰인 단어) 제거
    b. 4월 21일 ~ 4월 23일
    : 모델학습을 위해 텍스트 데이터를 시퀀스 데이터로 변환해줌(Keras Tokenizer 이용)
   
   4) 4월 24일 ~ 4월 30일
     a. 층화추출 (class label 94%:6%로 불균형)
     b. 변수 선택 (ex. 문자 메시지 길이, 형용사, 명사, 동사, 빈도)
       : Accuracy(Information Gain)를 확인하여 모델에 유의미한 영향력을 끼치는 변수 선택

   5) 5월 1일 ~ 5월 7일
     a. LightGBM 모델 구축 및 검증
     b. 하이퍼 파라미터 선택

   6) 5월 8일 ~ 5월 14일
     a. LSTM 모델 구축 및 검증
     b. 하이퍼 파라미터 선택
     c. LightGBM과 LSTM 모델 중 정확도, 속도를 고려하여 더 우수한 모델 선택

   7) 5월 15일 ~ 5월 21일
     a. LIME (Local Interpretable Model-agnostic Explanations) 학습
       (https://christophm.github.io/interpretable-ml-book/)
     b. LIME 듀토리얼 예제
       (https://github.com/marcotcr/lime/tree/ce2db6f20f47c3330beb107bb17fd25840ca4606)
     c. 6)의 c에 의하여 선택된 모델에 LIME 적용

   8) 5월 22일 ~ 5월 28일
     a. 카카오톡·라인 플러스 친구, 웹사이트 중 이번 모델에 적합한 플랫폼 선정
     b. 8)의 a에 의해 선정된 플랫폼 학습

   9) 5월 29일 ~ 6월 4일
     a. 웹 서비스 개발

   10) 6월 5일 ~ 6월 18일
     a. 웹서비스 개발 및 배포
     
----------
