2024-2 basic-ai-study WIL9
================================

* ## Object Detection
    * 객체(Classification)가 어느 위치(Localization)에 있는지 파악하는지 파악하고 class를 분류하는 task
    * Bounding Box로 여러 객체의 위치 출력(Bounding box regression)하고, 그 Box에 있는 객체가 각각 무엇인지 분류(Classification)해준다.
    * 딥러닝을 이용한 Object Detection은 2014년을 기준으로 나타나기 시작해, 크게 1-stage Detector와 2-stage Detector로 구분함.
    * ### 2-stage Detector
        * #### R-CNN
            * 기본적인 구조는 전체 task를 두 단계(2 stage)로 나눈다.
                * 물체의 위치를 찾는 Regional Proposal
                * 물체를 분류하는 Regional Classification
            * 다음 네 가지 모듈로 설명할 수 있다.
                * 이미지의 데이터와 레이블을 입력하여 카테고리와 무관하게 물체의 영역을 찾는 `Regional Proposal`
                * proposal된 영역으로부터 고정된 크기의 feature vector를 warping하여 CNN의 input으로 사용. `(pre-trained CNN)`
                * CNN을 통한 feature map을 활용하여 선형 지도학습 모델인 `SVM`(Support Vector Machine)을 통한 분류
                * Regressor를 통한 `Bounding Box Regression` 수행
        * #### Fast R-CNN
            * R-CNN의 문제점
                * RoI(Region of Interest)마다 CNN 연산을 함으로써 속도 저하
                * multi-stage pipelines로써 한번에 학습시키지 못함
            * Fast R-CNN은 다음으로 R-CNN의 문제점을 극복
                * RoI pooling
                * CNN 특징 추출로부터 classification, bounding box regression까지 하나의 모델에서 학습함
        * #### Faster R-CNN
            * Fast R-CNN은 Region Proposal로 사용된 Selective Search에 의해, detect time이 너무 길어짐.
            * Faster R-CNN은 Selective Search를 Region Proposal Network(RPN)으로 바꾸면서, 모든 요소들을 딥러닝만으로 구성한 최초의 end-to-end Object Detection 모델
    * ### 1-stage Detector
        * 2-stage Detector와 달리, Regional Proposal과 Classification이 한 stage에서 동시에 이루어짐.
        * #### YOLO (You Only Look Once)
            * 이미지 전체를 한번만 본다. CNN처럼 이미지를 분할해 해석하지 않음.
            * 기존 모델보다 빠른 성능으로, 실시간 객체 검출 가능
