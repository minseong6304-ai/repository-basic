## 제어공학 5주차 과제 ## 

### 2021732014 김민성 ### 

### P3.1 ###  
그림 p3.1에 스프링-질량-감쇠기 시스템이 주어져 있다. (a) 적당한 상태변수를 설정하라. (b) 상태변수로 표현된 1차 미분방정식을 구하라. (c) 상태미분방정식을 구하라.


<img width="378" height="190" alt="image" src="https://github.com/user-attachments/assets/717b3e86-8f91-46b4-a966-bd1b44846a32" />

$$
\text{state: } 
\begin{cases}
x_1(t) = y(t) \\
x_2(t) = \dfrac{dy(t)}{dt}
\end{cases}
$$


$$
M a_y = M \dfrac{d^2 y(t)}{dt^2} = F(t) - K y(t) - b \dfrac{dy(t)}{dt}
$$

$$
\Rightarrow M \dfrac{d^2 x_1(t)}{dt^2} = F(t) - K x_1(t) - b x_2(t)
$$

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

<img width="395" height="330" alt="image" src="https://github.com/user-attachments/assets/80ec174e-192d-4696-86e3-da2f569efea5" />
