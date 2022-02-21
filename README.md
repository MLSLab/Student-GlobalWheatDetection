# Student-GlobalWheatDetection
학생들 공부 자료

## 1. Data

### 1-1. Data Source 별 이미지 개수 확인
![image](https://user-images.githubusercontent.com/32845598/154924646-84476b8c-9008-4293-a290-77eb314ac75d.png)


### 1-2. Train Data 예제
![image](https://user-images.githubusercontent.com/32845598/154928740-f4b4ef0a-2c26-4087-8ebf-02095fdfbe42.png)


### 1-3. Test Data 예제
![Untitled (2)](https://user-images.githubusercontent.com/32845598/154924771-e815838c-f211-4292-ace3-a284b616de78.png)

## 2. Model : U-net
적은 수의 데이터로도 정확한 Segmentation 이 가능
![Untitled (4)](https://user-images.githubusercontent.com/32845598/154929218-9aef8b69-a61a-4bf8-aecc-97ab6b755a07.png)

**U-net이 개선한 점**
- `속도 향상` : sliding window 대신 patch 탐색 방식 사용
- `context 인식` : contracting path (encode) 에서 이미지의 context를 포착
- `localization 간의 trade-off 해결` : expanding path (decode) 에서 upsampling 한 feature map을 contracting path 의 context와 결합해 localization 정확도를 높임. 기존의 방식은 한 번에 넓은 구역을 보면 전체적인 그림의 인식 확률은 좋아지지만 localization 이 부족해지고, 좁은 구역을 보면 세분화된 localization 이 가능하지만, 인식률이 떨어지는 단점이 있었음.


**patch** **(tile)**
이미지 인식 단위. 

sliding window 방식을 사용할 경우에는 이미 사용한 이미지 영역을 다음에도 다시 사용하게 된다. 
반면, patch 탐색 방식은 이미지를 격자 모양으로 사용해 중첩된 이미지 사용을 피한다. **(속도향상!)**
![image](https://user-images.githubusercontent.com/32845598/154929016-d440e9ed-2c9c-4f03-b5d3-8b45e20146a6.png)


## 3. 예측

예측된 mask 와 bounding box 비교

![image](https://user-images.githubusercontent.com/32845598/154929504-5d814434-d625-47c1-a1c4-5da8713cb040.png)




#### 참고
https://www.kaggle.com/c/global-wheat-detection/data

#### 2021 GWD dataset
https://www.aicrowd.com/challenges/global-wheat-challenge-2021#dataset


