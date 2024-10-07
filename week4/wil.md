2024-2 basic-ai-study WIL4
================================

* ## 손실 함수 (Loss Function)
    * ### Weight Matrix
        * 입력 이미지를 정확하게 분류하기 위해 사용
        * 최적화 방법
            * Loss Function 사용 : 현재 Weight Matrix의 예측과 실제 정답 간의 차이(오차)를 수치화한다.
            * 측정 결과를 이용하여 Weight Matrix의 값을 업데이트
            * Loss를 최소화하여 분류 정확도를 높이기 위함이 목적
        * 문제의 특성과 데이터 유형에 따라, 적합한 Loss Function을 선택한다.
            * 회귀 문제에서 사용되는 Loss : MSE(Mean Squared Error)
            * 분류 문제에서 사용되는 Loss : SVM Loss(Support Vector Machine에서 사용되는 hinge loss), Cross-Entrophy Loss
    
* ## Regularization
    * ### Overfitting (과적합)
        * 모델이 훈련 데이터에 너무 가깝게 맞춰지면, 실제 입력 데이터에 대해 어떻게 대응해야 할지 모를 경우 발생
        * 훈련 데이터에 너무 익숙해지다 보면, 실제 데이터에 대해서는 높은 예측 오차를 보일 수 있다.
        * 해결 방법 : Regularization으로 모델의 복잡도를 제어, 과적합을 방지할 수 있다.
        * #### L2 Regularization
            * 기존 cost function에 가중치의 제곱을 포함하여 더하여 학습시킴.
            * 큰 가중치에 더 큰 페널티 부과. 극단적인 가중치를 피하고, 모든 특성이 적당히 기여하도록 유도
        * #### L1 Regularization
            * 기존 cost function에 가중치의 크기가 포함되어, 가중치가 너무 크지 않은 방향으로 학습되도록 함.
            * 분류기가 복잡하다고 느껴질 때 사용. 가중치 값으로 0이 많도록 하여 보다 단순한 식을 만들어줌.