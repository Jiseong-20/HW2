# 2020732065_정지성, 5주차 1차시 강의요약
- <img src="https://github.com/user-attachments/assets/0a3874fc-fb6e-4ac5-bbb0-209186048138" width="400" height="400" />
- 상태변수 $x_1(t), x_2(t)$ 를 설정해서 미분방정식의 차수를 낮추는 효과 -> 컴퓨터에게 계산시키기 편해진다.
- (이때 사진의 상황에서는 2차 미분방정식이기 때문애 두 개의 state를 설정)
- <img src="https://github.com/user-attachments/assets/6c0e0d60-8b18-4c13-bf50-16835f665dba" width="400" height="200" />
- 상태변수를 설정할 떄는 설정하고 싶은대로 설정해도 되지만 두 상태변수가 독립적이어야 한다.
- 예를 들어 사진의 회로에서 $i_L$을 하나의 상태변수로 하고 다른 하나를 $V_O$로 한다면 두 상태변수는 $V_O = i_L*R$이라는 관계를 갖는다.
- 이때 R은 상수이므로 둘은 독립적이지 않아서 올바르지 않은 상태변수 설정이다.
### 미분방정식의 해
- 1차 미분방정식 x′(t) = ax(t) + bu(t)에 대해서 이 미분방정식의 해는 $x(t) = \phi (t)x(0) + \int \phi (t-\tau )bu(\tau )dt$가 나온다.
- 즉 state variable을 이용하면 미분방정식의 해가 초기상태와 input에 $\phi (t)$가 곱해진 형태로 나온다는 것을 알 수 있다.
- 이때 n차 미분방정식에 대해서 
- 이 n차 미분 방정식의 해와 출력은 다음과 같이 행렬을 이용해 나타나진다.
- $x′(t) = Ax(t) + Bu(t)$ -- state differential equation
- $y(t) = Cx(t) + Du(t)$ -- output equation
- 그리고 이 두 식을 합쳐서 State space equation이라 부른다.
- (이때 A, B, C, D 와 x(t), u(t) 모두 행렬이다.)
- n차 미분방정식의 해: $x(t) = e^{At}x(0)+\int e^{A(t-\tau )}Bu(\tau )d\tau $
- 라플라스 변환을 취하면 $X(s)=[sI-A] ^{-1}x(0)+[sI-A] ^{-1}BU(s)$
- $\phi (s)= [sI-A] ^{-1}$
- $\phi (s)$에 라플라스 역변환을 취하면 $\phi (t)이다.$
- 이때 $\phi (t)$는 State transition matrix 라고 한다.

### Matlab을 이용해 State space equation 그래프 그리기
- sys = ss(A, B, C, D); --> 행렬 A, B, C, D를 이용해 State space equation 설정
- x0 = [0.1 0 0 0];  -->초기값 설정
- initial(sys, x0, [0,5]);  -->sys를 이용해 x_0의 초기값으로 0~5초를 실행한다.
