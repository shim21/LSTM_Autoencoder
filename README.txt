# LSTM_Autoencoder

시계열 데이터(Sequence data)에 Encoder-Decoder LSTM 아키텍처를 적용하여 구현한 오토인코더
--> 입력 시퀀스가 순차적으로 들어오고, 마지막 입력 시퀀스가 들어온 후 디코더는 입력
시퀀스를 재생성하거나 혹은 목표 시퀀스에 대한 예측을 출력
--> LSTM_Autoencoder를 통해 고전적인 머신러닝 기반의 회귀모델(Linear regressor, SGD regressor 등등)처럼 regressor 문제에 활용이 가능합니다.

LSTM Autoencoder의 종류
1. Reconstruction LSTM Autoencoder : 입력과 최대한 유사하게 출력을 디코딩하는 LSTM Autoencoder
2. Prediction LSTM Autoencoder : 시계열적 예측을 위한 LSTM 구조이며 입력 시퀀스는 현재 지점(t), 출력 시점은(t+1)으로 두어 한 시점 앞을 학습하도록 데이터를 구성
--> AE는 학습시에 인코더에는 t시점이 입력되지만 디코딩 후에는 (t+1)시점과 reconstruction error를 계산하여 결국 t시점이 t+1 시점을 학습하게 된다.
3. Composite LSTM Autoencoder : Reconstruction과 Prediction모델을 통합한 모델, 결과적으로 Reconstruction결과와 Prediction결과가 함께 출력
