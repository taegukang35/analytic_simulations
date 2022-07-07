import numpy as np
import matplotlib.pyplot as plt

# 초기값 세팅
x0, v0 = 5, 15
b, m, k = 2, 1, 10
h = 0.1
t = 0
maxt = 10

# f(x,v) 구현
def f(x, v):
    return -(b * v + k * x) / m

# 출력할 그래프 관련 설정
plt.axis([0, maxt+1, -(x0 + 4), x0 + 4])
plt.xlabel('t')
plt.ylabel('x')

# runge-kutta method 구현
# v_n+1 = v_n + hT_4(x_n,v_n,h)
# x_n+1 = x_n + hv_n
# t = t+h 로 구현
while t < maxt:
    k1 = f(x0, v0)
    k2 = f(x0 + h / 2., v0 + (k1 * h) / 2.)
    k3 = f(x0 + h / 2., v0 + (k2 * h) / 2.)
    k4 = f(x0 + h, v0 + (k3 * h))
    v1 = v0 + h / 6. * (k1 + (2 * k2) + (2 * k3) + k4)
    x1 = x0 + h * v0
    plt.scatter(t, x1, color='b')
    plt.pause(0.001)
    print(f"{x1} {v1}")
    x0, v0 = x1, v1
    t += h
plt.pause(3)
