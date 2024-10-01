2024-2 basic-ai-study WIL2
================================

* ## 이미지 분류 (Image Classification)
    * 컴퓨터가 입력된 이미지를 보고 어떤 클래스(카테고리)에 속하는지 분류하는 문제
    * 일반적으로 이미지 분류를 수행하는 모델은 뉴럴 네트워크를 사용한다. 이미지에서 특징(feature)을 추출하여, 이를 이용해 이미지 분류를 수행한다.
    * 이미지 분류를 수행하는 딥러닝 모델은 주로 CNN을 이용한다.
* ### 이미지 분류 활용 예시
    * 온라인 쇼핑 사이트에서의 물품 이미지를 통한 카테고리 분류
    * 검색 엔진에서의 사진 인식을 통한 웹 검색 기능 구현
    * 자율 주행 분야에서의 3D 이미지 분류를 통해 객체, 환경 인식

* ## 합성곱 신경망(CNN, Convolutional Neural Network)
    * 딥러닝에서 이미지, 영상 데이터를 처리할 때 사용하는, Convolution이라는 전처리 작업을 포함한 신경망 모델

* ### CNN 이전의 신경망 모델, FNN(Fully-Connected Neural Network)
    * 2차원 형태의 이미지를 입력받으면, 이를 flatten 시켜, 처리한다.
    * 1차원 형태의 데이터로 변환하는 과정에서 이미지의 공간적, 지역적 정보의 손실이 발생하게 된다.
    * 추상화 과정 없이 바로 연산하기 때문에, 학습시간과 능률의 효율성이 저하된다.
    * 위의 문제점들을 해결하기 위해 고안한 모델이 CNN이다.

* ### CNN의 구조
* #### Convolutional layer
    * 입력 데이터에 다양한 필터를 적용하여 특징을 추출하여, Feature map을 생성한다.
    * 필터에 다양한 활성함수를 적용하여, 여러 픽셀들의 연산(합성곱, Convolution)을 통해 단일 픽셀 뿐만이 아닌, 주변 픽셀들과의 연관관계도 고려하여 특징을 추출할 수 있다.

* #### Pooling layer
    * Pooling 방식
        * Max-pooling : 해당 구역에서 최대값을 찾아 pooling
        * Average-pooling : 해당 구역의 평균값을 계산하여 pooling
    * Pooling 하는 이유
        * feature map의 크기가 너무 크면, ovefitting이 발생할 가능성이 높아진다.
            * overfitting : 훈련용 데이터에 너무 익숙해진 모델이, 실제로 주어지는 추가 데이터에서의 정확도가 오히려 낮아지는 현상
        * Pooling을 통해 feature map의 크기를 조절하여, overfitting을 방지하는 것이다.
    * CNN은 Convolution layer와 Pooling layer의 반복으로 구성된다.
* #### Fully Connected Layer
    * 추출된 feature를 종합해 최종적인 분류를 수행한다.