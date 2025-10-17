## 제어공학 5주차 과제  

### 2021732014 김민성  

### P3.1   
그림 p3.1에 스프링-질량-감쇠기 시스템이 주어져 있다. (a) 적당한 상태변수를 설정하라. (b) 상태변수로 표현된 1차 미분방정식을 구하라. (c) 상태미분방정식을 구하라.


<img width="378" height="190" alt="image" src="https://github.com/user-attachments/assets/717b3e86-8f91-46b4-a966-bd1b44846a32" />
(a)

$$
\text{state: } 
\begin{cases}
x_1(t) = y(t) \\
x_2(t) = \dfrac{dy(t)}{dt}
\end{cases}
$$

(b)

$$
M a_y = M \dfrac{d^2 y(t)}{dt^2} = F(t) - K y(t) - b \dfrac{dy(t)}{dt}
$$

$$
\Rightarrow M \dfrac{d^2 x_1(t)}{dt^2} = F(t) - K x_1(t) - b x_2(t)
$$

(c)

$$
X(t) = 
\begin{bmatrix}
x_1(t) \\
x_2(t)
\end{bmatrix} =
\begin{bmatrix}
x_1(t) \\
x_1'(t)
\end{bmatrix}
$$

$$
X'(t) =
\begin{bmatrix}
x_1'(t) \\
x_2'(t)
\end{bmatrix} =
\begin{bmatrix}
0 & 1 \\
-\dfrac{K}{M} & -\dfrac{b}{M}
\end{bmatrix}
X(t)
+
\begin{bmatrix}
0 \\
\dfrac{1}{M}
\end{bmatrix}
F(t)
$$

$$
y(t) =
\begin{bmatrix}
1 & 0
\end{bmatrix}
X(t)
$$

---
### P3.3   
그림 P3.3과 같은 RLC회로가 주어졌다. 상태변수 X1(t) = iL(t), X2(t) = Vc(t)로 설정하고 상태미분방정식을 구하라.  

<img width="442" height="276" alt="image" src="https://github.com/user-attachments/assets/7559a77e-1ada-4ab0-b9ba-a7a60549879c" />
 

$$
x_1(t) = i_L(t), \quad x_2(t) = v_C(t)
$$


$$
v_1(t) - L \dfrac{di_L(t)}{dt} + v_C(t) - v_2(t) = 0
$$

$$
① L \dfrac{dx_1(t)}{dt} = v_1(t) - v_2(t) + x_2(t) \Rightarrow \dfrac{dx_1(t)}{dt} = \dfrac{v_1(t)}{L} - \dfrac{v_2(t)}{L} + \dfrac{x_2(t)}{L} \
$$


#### \( V(t) \) 에서 KCL을 하면

$$
i_L(t) = i_R(t) + i_C(t)
$$

$$
i_L(t) = \dfrac{v_2(t) - v_1(t)}{R} - C \dfrac{dv_C(t)}{dt}
$$

$$
② C \dfrac{dx_2(t)}{dt} = \dfrac{v_2(t)}{R} - \dfrac{v_1(t)}{R} - x_1(t) \Rightarrow \dfrac{dx_2(t)}{dt} = \dfrac{v_2(t)}{RC} - \dfrac{v_1(t)}{RC} - \dfrac{x_1(t)}{C}
$$


#### 식 (①), (②)으로 행렬방정식을 세우면

$$
\dot{X}(t) =
\begin{bmatrix}
0 & \dfrac{1}{L} \\
-\dfrac{1}{C} & -\dfrac{1}{RC}
\end{bmatrix}
X(t)
+
\begin{bmatrix}
\dfrac{1}{L} & -\dfrac{1}{L} \\
-\dfrac{1}{RC} & \dfrac{1}{RC}
\end{bmatrix}
V(t)
$$

$$
Y(t) =
\begin{bmatrix}
0 & -1
\end{bmatrix}
X(t)
+
\begin{bmatrix}
0 & 1
\end{bmatrix}
V(t)
$$


$$
X(t) =
\begin{bmatrix}
x_1(t) \\
x_2(t)
\end{bmatrix},
\quad
V(t) =
\begin{bmatrix}
v_1(t) \\
v_2(t)
\end{bmatrix}
$$

---

### P3.5
그림 P3.5에 페루프 제어시스템이 주어져있다. (a) 폐루프 전달함수 T(s) = Y(s)/R(s)를 구하라. (b) 상태변수 모델을 구하고 위상변수형 블록선도를 작성하라.

<img width="644" height="185" alt="image" src="https://github.com/user-attachments/assets/a5968749-d841-43a9-b475-4f5991d52d3b" />


#### (a) 폐루프 전달함수 T(s) = Y(s)/R(s)를 구하라.

$$
G(s) = \dfrac{s + 2}{(s + 8)(s - 3)} 
= \dfrac{s + 2}{s^3 + 5s^2 - 24s}
$$

$$
H(s) = 1
$$

$$
T(s) = \dfrac{G(s)}{1 + G(s)H(s)} 
= \dfrac{\dfrac{s + 2}{s^3 + 5s^2 - 24s + 2}}{1 + \dfrac{s + 2}{s^3 + 5s^2 - 24s}}
= \dfrac{s + 2}{s^3 + 5s^2 - 23s + 2}
$$




#### (b) 상태변수 모델을 구하고 위상변수형 블록선도를 작성하라.

$$
T(s) = \dfrac{Y(s)}{R(s)} = 
\dfrac{(s + 2)Z(s)}{(s^3 + 5s^2 - 23s + 2)Z(s)}
$$


$$
Y(s) = (s + 2)Z(s), \quad 
R(s) = (s^3 + 5s^2 - 23s + 2)Z(s)
$$


#### 라플라스 역변환하면

$$
Y(t) = z'(t) + 2z(t) = 2x_1(t) + x_2(t)
$$

$$
R(t) = z'''(t) + 5z''(t) - 23z'(t) + 2z(t)
$$



$$
x(t) =
\begin{bmatrix}
x_1(t) \\
x_2(t) \\
x_3(t)
\end{bmatrix}=
\begin{bmatrix}
z(t) \\
z'(t) \\
z''(t)
\end{bmatrix}=
\begin{bmatrix}
z(t) \\
x_1'(t) \\
x_2'(t)
\end{bmatrix}
$$

$$
z'''(t) = x_3'(t)
= r(t) - 5x_3(t) + 23x_2(t) - 2x_1(t)
$$


$$
x'(t) =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-2 & 23 & -5
\end{bmatrix}
x(t)
+
\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix}
r(t)
$$


$$
y(t) =
\begin{bmatrix}
2 & 1 & 0
\end{bmatrix}
X(t)
$$

---

### P3.12
<img width="386" height="139" alt="image" src="https://github.com/user-attachments/assets/f4b70ad8-a4b3-4cec-8631-3a65ac0d6f2c" />

#### (a) 상태공간모델을 구하라.

$$
T(s) = \dfrac{Y(s)}{R(s)} = \dfrac{8s + 40}{s^3 + 12s^2 + 44s + 48} \cdot \dfrac{Z(s)}{Z(s)}
$$


$$
R(s) = (s^3 + 12s^2 + 44s + 48)Z(s), \quad 
Y(s) = (8s + 40)Z(s)
$$


#### 라플라스 역변환하면

$$
r(t) = z'''(t) + 12z''(t) + 44z'(t) + 48z(t)
$$

$$
y(t) = 8z'(t) + 40z(t)
= 40x_1(t) + 8x_2(t)
$$


$$
X(t) =
\begin{bmatrix}
x_1(t) \\
x_2(t) \\
x_3(t)
\end{bmatrix}
=\begin{bmatrix}
z(t) \\
z'(t) \\
z''(t)
\end{bmatrix}
=\begin{bmatrix}
z_1(t) \\
x_1'(t) \\
x_2'(t)
\end{bmatrix}
$$


$$
x_3'(t)
= z'''(t)
= r(t) - 12z''(t) - 44z'(t) - 48z(t)
$$

$$
= r(t) - 12x_3(t) - 44x_2(t) - 48x_1(t)
$$


$$
X'(t) =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-48 & -44 & -12
\end{bmatrix}
X(t)
+
\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix}
r(t)
$$


$$
y(t) =
\begin{bmatrix}
40 & 8 & 0
\end{bmatrix}
X(t)
$$

#### (b) 상태이천행렬을 구하라.

$$
A =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-48 & -44 & -12
\end{bmatrix}
$$

$$
sI - A =
\begin{bmatrix}
s & 0 & 0 \\
0 & s & 0 \\
0 & 0 & s
\end{bmatrix}-
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-48 & -44 & -12
\end{bmatrix}
=\begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s + 12
\end{bmatrix}
$$

$$
\Phi(s)
= [sI - A]^{-1}
= \frac{1}{s^3 + 12s^2 + 44s + 48}
\begin{bmatrix}
s(s^2 + 12s + 44) & 48 & 0 \\
0 & s(s^2 + 12s) & 44s + 48 \\
48 & 44s & (s + 12)s^2
\end{bmatrix}
$$

#### 이는 손으로 풀 수 없기 때문에, 매트랩으로 계산하면

$$
\Phi(t) = \begin{bmatrix} 
e^{-6t} - 3e^{-4t} + 3e^{-2t} & \frac{3}{4}e^{-6t} - 2e^{-4t} + \frac{5}{4}e^{-2t} & \frac{1}{8}e^{-6t} - \frac{1}{4}e^{-4t} + \frac{1}{8}e^{-2t} \\
-6e^{-6t} - 12e^{-4t} - 6e^{-2t} & -\frac{9}{2}e^{-6t} + 8e^{-4t} - \frac{5}{2}e^{-2t} & -\frac{3}{4}e^{-6t} - e^{-4t} - \frac{1}{4}e^{-2t} \\
36e^{-6t} - 48e^{-4t} + 12e^{-2t} & 27e^{-6t} - 32e^{-4t} + 5e^{-2t} & \frac{9}{2}e^{-6t} - 4e^{-4t} + \frac{1}{2}e^{-2t}
\end{bmatrix}
$$

---

### P3.17

<img width="452" height="237" alt="image" src="https://github.com/user-attachments/assets/395928ce-a55a-4c30-9ef1-e744a47129a7" />

$$
A = \begin{bmatrix}
0 & 1 & 0\\
0 & 0 & 1\\
-48 & -44 & -12
\end{bmatrix}, 
B = \begin{bmatrix}
0\\
0\\
1
\end{bmatrix}  
C = \begin{bmatrix}
0 & 1 & 0
\end{bmatrix},
D = 0
$$  


$$
x'(t) = Ax(t) + Bu(t)
$$

$$
y(t) = Cx(t)
$$  

#### 이를 라플라스 역변환하면,

$$
sX(s) = AX(s) + BU(s)
$$  

$$
Y(s) = CX(s)
$$

$$
[sI-A]X(s) = BU(s)
$$  

$$
X(s) = [sI - A]^{-1} BU(s) \text{ 에서, } \Phi(s) = [sI - A]^{-1}
$$  

$$
\Phi(s) = 
\begin{bmatrix}
s-1 & -1 & 1 \\
-4 & s-3 & 0 \\
2 & -1 & s-10
\end{bmatrix}^{-1} =
\begin{bmatrix}
\dfrac{s^2 - 13s + 30}{s^3 - 14s^2 + 37s + 20} &
\dfrac{s - 11}{s^3 - 14s^2 + 37s + 20} &
\dfrac{-s + 3}{s^3 - 14s^2 + 37s + 20} \\
\dfrac{4s - 40}{s^3 - 14s^2 + 37s + 20} &
\dfrac{s^2 - 11s + 8}{s^3 - 14s^2 + 37s + 20} &
\dfrac{-4}{s^3 - 14s^2 + 37s + 20} \\
\dfrac{-2s + 10}{s^3 - 14s^2 + 37s + 20} &
\dfrac{s - 3}{s^3 - 14s^2 + 37s + 20} &
\dfrac{s^2 - 4s - 1}{s^3 - 14s^2 + 37s + 20}
\end{bmatrix}
$$

$$
X(s) = \Phi(s) BU(s)  
Y(s) = C \Phi(s) BU(s)
$$  


#### 이는 손으로 풀 수 없기 때문에, 매트랩으로 계산하면


$$
G(s) = C(sI-A)^{-1}B = \frac{-4s+12}{s^3 - 14s^2 + 37s +20}
$$

