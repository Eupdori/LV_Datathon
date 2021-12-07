# 팀명 : 읍도리s

## 가상환경
가상환경 설정은 첨부되어 있는 환경설정.zip 파일안에 환경설정.txt 파일을 보고 하시면 됩니다.

## 학습코드
학습 코드는 제출한 압축 파일을 해제하시면 code라는 폴더안에 Train_code 폴더안에 있습니다.

## 모델 Weight
모델 Weight 파일은 result 폴더안 model_save폴더안에 있습니다.

## 코드 실행 방법
1. 압축 해제후 data/raw_test_data/ 폴더안에 대회에서 제공해준 데이터처럼 A2C, A4C 각각 폴더에 .png, .npy 파일을 업로드해주세요. cf) A2C, A4C 폴더는 만들어두었습니다.
2. 가상환경 접속후 터미널에서 jupyter notebook 입력하여 jupyter notebook 실행
3. code 폴더안 Test_Data_Preprocessing.ipynb를 실행후 순서대로 코드 실행
4. Test_Data_Preprocessing.ipynb 코드 실행 결과 테스트 데이터에 대한 npy파일은 data/test_dataset/ 폴더안에 test_image.npy, test_label.npy 이름으로 저장됩니다.
5. Prediction_Code.ipynb 코드 실행 후 순서대로 코드 실행시 마지막 셀에서 A2C, A4C에 대한 각각의 결과가 표시됩니다.


## 모델 설명

본 참가팀에서 제출한 모델은 A2C, A4C 이미지를 동시에 학습이 가능한 Siamese Neural Networks 구조를 가지고 있습니다.

Siamese Neural Networks에서 사용한 베이스라인 모델은 U-Net, Residual U-Net, Attention U-Net, RA U-Net(Residual Attention) 총 4가지 모델에 대해 성능 테스트후 Attention U-Net을 사용하였으며, 각 모델의 decoder에서 두번째 layer에서 auxiliary loss를 계산하고 마지막 layer에서 얻은 loss와 더하여 최종 loss를 계산하였습니다.

최종적으로 본 참가팀은 A2C, A4C 이미지를 동시에 학습이 가능한 Siamese Neural Networks에 auxiliary loss를 사용하여 모델의 학습 시간을 단축시키며, 모델의 분할 정확도를 향상 시킨 모델을 개발하였습니다.
