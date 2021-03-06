# deep_learning_with_python
[케라스 창시자에게 배우는 딥러닝] 책을 가지고 공부합니다.

## 텐서(tensor)
> 다차원 넘파이 배열으로 머신 러닝의 기본 구성요소 입니다. 텐서는 데이터를 위한 컨테이너입니다.
-------------------------------------------------------------------
> ### 스칼라(0D 텐서)
> 하나의 숫자만 담고있는 텐서를 스칼라(또는 스칼라텐서, 0차원 텐서, 0D텐서)라고 부릅니다. ndim속성을 사용하면 넘파이 배열의 축 개수를 확인할 수 있습니다. 스칼라 텐서의 축 개수는 0입니다.(ndim == 0). 텐서의 축 개수를 랭크라고도 부릅니다.
```
>>> import numpy as np
>>> x = np.array(12)
>>> x
array(12)
>>> x.ndim
0
```
> ### 벡터(1D 텐서)
------------------------------------------------------------------
> 숫자의 배열을 벡터 또는 1D텐서라고 부릅니다. 축은 한개를 가지고 있습니다.
```
>>> x = np.array([1,3,2,4,5])
>>> x
array([1,3,2,4,5])
>>> x.ndim
1
```
> 이 벡터는 5개의 원소를 가지고 있기 때문에 5차원 벡터라고 부릅니다.
> ### 벡터 데이터 : 대부분의 경우에 벡터 데이터가 쓰인다. 2D텐서로 인코딩된다. 첫번째 축은 샘플축, 두번째 축은 특성축(feature axis)이다. 
> 벡터 데이터의 예를 들어보자면
* 사람의 나이, 우편번호, 소득으로 구성된 인구 통계 데이터, 각 사람은 3개의 값을 가진 벡터로 구성되고 10만명이 포함된 전체 데이터 셋은 (100000, 3)크기의 텐서에 저장될 수 있다.
* 공통 단어 2만개로 만든 사전에서 각 단어가 등장한 횟수로 표현된 텍스트 데이터셋. 각 문서는 2만개의 원소를 가진 벡터로 인코딩될 수 있을 때, 500개의 문서로 이루어진 데이터셋은 (500, 20000) 크기의 텐서로 저장될 수 있다.
------------------------------------------------------------------
> ### 행렬(2D 텐서)
> 벡터의 배열이 행렬또는 2D텐서입니다. 행렬에는 행(row)와 열(colunm)이라는 2개의 축이 있습니다. 행렬은 숫자가 채워진 사각 격자라고 생각할 수 있습니다.
```
>>> np.array([[1,2,3,4,5],
              [6,7,8,9,10],
              [11,12,13,14,15]])
>>> x.ndim
2
```
> 첫번째 축에 놓여있는 원소를 행이라 부르고, 두 번째 축에 놓여있는 원소를 열이라고 부릅니다. 앞의 코드에서는 x의 첫번째 행은 [1,2,3,4,5]이고 첫번째 열은 [1,6,11]입니다.
-------------------------------------------------------------
> ### 3D텐서와 고차원 텐서
> 이런 행렬들을 하나의 새로운 배열로 헙차면 숫자가 채워진 직육면체 형태로 해석할 수 있는 3D텐서가 만들어 집니다. 넘파이에서 3D텐서를 나타내면 다음과 같습니다.
```
>>> x = np.array([[[1,2,3,4,5],
              [6,7,8,9,10],
              [11,12,13,14,15]],
              [[13,2,3,4,5],
              [6,74,8,9,10],
              [115,12,13,14,15]]
              [[1,2,3,4,5],
              [6,7,8,9,10],
              [11,12,13,14,15]]])
>>> x.ndim
3
```
> 3D텐서들을 하나의 배열로 합치면 4D텐서를 만드는 식으로 고차원 텐서를 만들 수 있습니다. 딥러닝에서는 보통 0D에서 4D까지를 다루지만, 동영상을 다룰때는 5D까지 가기도 합니다.
-----------------------------------------------------------------
## 팁 : 전치를 사용해 행과 열을 바꿀수 있음
```
>>> x = np.zeros((300, 20))
>>> x = np.transpose(x)
>>> print(x.shape)
(20, 300)

```
