#강의정리

1. 캐글 튜토리얼 대회
2. 대회한두개 참여해보니... 금방 들게되더라
3.이론은 최소화 대회는 많이..

- 주최자가 train test나눈방법대로 train set을 쪼갠다
-데이터 전처리단계에서 fold나눠서 파일로 저장뒤 이 고정fold를 계속 이용한다 
- sklearn의 kfold, groupkfold, stratifiedkfold패키즈를 사용 

out of fold, 5 fold 모든 대회에서 쓸수있으면 쓰는게 고득점에 좋다. 
fold= 데이터나누는 조각 

5fold+valid를 각모델별로 만들어서 스태킹, 앙상블로 사용한다(oof = out of fold)


베이스라인작성: 재사용 가능한 뼈대코드를 만들자
자신만의 뼈대코드를 만들어놓으면 좋은점
1. 여러 아이디어를 추가하는 것이 쉬움
2. 코드의 사용을 거듭하면서 코드를 지속적으로 업그레이드 가능
3. 새 대회에 참가할 때, 이전대회 코드를 살짝 수정해서 베이스라인 작성 가능.. 
4. 이렇게 짜놓은 베이스라인코드는 내가 모두이해한것이기때문에 활용이 쉽다.


대회참가시에 이전대회의 코드를 복사해와서 내 뼈대코드를 참조해서 다시 짜서 빠르게 돌려본다.
eda.ipynb - 데이터 구성확인, 주피터 노트북으로 간단한 체크 할대 이용
preprocess.py - 테이터 빠르게 로드할 수있는 형태로 전처리 (로더가 데이터모델 학습률 따라갈수있게끔,,가끔 못다라서 gpu학습률을 떨구는일이있다)
data.py - 데이터로더
data_check.ipynb - 데이터로더에서 나오는 값들 확인
model.py - 딥러닝 모델 아키텍처, 로스 정의
train.py - 학습데이터경로, 모델 저장경로, 하이퍼파라미터들 받아서 모델 학습 및 저장
predict.py - 예측할 데이터가 있는 경로, 모델경로, 예측결과를 저장할 경로 받아서 예측 수행
stack.py - 스태킹용 모델학습 및 저장 or 학습된 모델 로드 후 예측 


점수올리기
베이스라인- 버그프리(대회의 캐글러 공유코드, 아님 데이터보고 확인)
적절한모델을 구현만해놔도 메달권 가능하다.
(스킬셋, 포럼, 지난대회 솔루션, 데이터특성, 논문 등..) => 아이디어로 코드 구현해서 =>cv체크=>lb체크=>쓸것인지결정(리더보드 점수가 올라가는지?)



앙상블 - 점수를 올리는 보증수표 
+ 평균/가중평균/스태킹
+ n-fold앙상블, n-seed앙상블, 다양한모델별 앙상블 

애용하는 파이썬 라이브러리
딥러닝 - pytorch, pytorch lightning
기본 - jupyterlab, pandas, numpy, sklearn, matplotluib, seaborn
gbm- lightgbm, dmlcxgboost, catboost
vision- rwightman/pytorch-image-models, albumentations, opencv, segmatation models
nlp - transformers
기타 - weights & biases, optuna(하이퍼파라메터 튜닝툴) 


메달권 솔루션순서
- 스킬셋(캐글에서 사골인 스킬)
- 포럼
- 이전대회 솔루션
- 데이터특성(복잡한 베이스라인에서 train, test환경을 동일화하는것) 
- 엔지니어링(버그프리코드)
- 논문
- 장비

 

