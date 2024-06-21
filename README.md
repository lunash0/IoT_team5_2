<<<<<<< HEAD
## Stage 1
In our 2-staged approach, this model is the first model, finding the eyes in any given frame. The model is trained on 532 images and validated with another 354.

<memo>
=======
#  Eye tracking AI

This project is part of the mobile systems engineering class _Embedded systems and IoT_ at Dankook university (단국대학교).
We are team 5 and are working on an algorithm/AI-based program to detect the direction a person is looking to, also known as eye tracking. Our motivation is to help people improve their presentation skills by collecting data about where they look, i.e. the audience, the screen or their notes, but we also see many more uses like helping drivers stay focused on the street or companies testing their advertisement and whether it "catches" the public's eye.

## Overview

We use a 2-staged structure to simplify each module and also keep them modular, so that retraining one model should not impact the other model. In this particular case, we are using the first stage to find any eyes in the current frame, and the second stage takes the eye-cutout, tries finds the pupil, and and with that information figure out where the person is looking.
There is a lot of room to improve detection without changing the models, since knowing that humans have two eyes, sanity checks through cross-checking can be performed on the output. 

![Concept poster of the steps involved in detecting the person's eyes and where they look](/team5-poster.png)

## Stage 1
Stage 1 uses [YOLOv8 by ultralytics](https://github.com/ultralytics/ultralytics) to find any eyes in the frame. The dataset used is a sub-selection of the dataset Labeled Faces in the Wild, short [LFW](https://www.kaggle.com/datasets/atulanandjha/lfwpeople), trained in [colab.research.google.com](https://colab.research.google.com). The model is trained on 532 images and validated with another 354. The exact subset used, split by training and validation, can be found [here](/stage-1/YOLODataset/images). 

When the trained model is run with webcamTest.py, images are retrieved from the connected camera (by default the one with id=0), each frame is then checked for the presence of eyes. The frame together with the detection box are then displayed in an application window.

The following image is from the window generated by webcamTest.py using a virtual camera input from obs studio. The image is part of the training dataset.

![Screenshot of a person whose eyes are being detected using this AI model](/stage-1/김대중%20eye%20detection.PNG)

The same way the box is drawn, these boxes can be saved as images to be used by stage-2.
>>>>>>> b6c9a33ad11beb513ea69635dd4c1fdcafa4e392

- Introduction
    - Training data source (link if you use open data from internet)
      If you gather data by yourself, describe about the data set. (Number of data, kind of labels and how you can gather the data)
      - Representative block diagram or picture of your project
  - above Youtube link
<br/>
<br/>
---
<br/>
<br/>  

<<<<<<< HEAD
# 1. Project Introduction
욜로v8을 활용하여 

# 2. Custom Dataset - ??

# 3. Training

# 4. Our Algorithms

# 5. Youtube Link for Deomo
=======
Stage 2는 눈만을 인식하던 eye detection에서 더 나아가 눈동자까지 인식하여 더 완벽한 인식 시스템을 개발하고, 그에 맞춰서 자동화된 눈동자 감지 및 피드백 알고리즘을 개발하고자 합니다.

이 작업을 위한 학습 데이터세트는 다음과 같이 라벨링 되었습니다. ![image](https://github.com/lunash0/IoT_team5/assets/109780232/09607791-9206-428b-9543-9311e58f0a6f)

또한, 더 신뢰성 있는 인식을 위하여 다음과 같은 추가적인 절차를 작업하였습니다.

- 중복되는 값이 없도록 high confidence를 갖는 눈동자와 눈 하나씩만 인식하게끔 설정
- 한 쌍의 눈이 아닌 오른쪽 혹은 왼쪽 눈을 두번 인식하는것을 막고 한쌍의 눈을 인식하게끔 설정

![KakaoTalk_20240611_182641369](https://github.com/lunash0/IoT_team5/assets/109780232/9ac3dd58-9f1d-4286-9e87-2d93430163a8)

이와 같은 절차를 통해 눈동자와 눈의 인식은 다음과 같이 이루어졌습니다.

>>>>>>> b6c9a33ad11beb513ea69635dd4c1fdcafa4e392