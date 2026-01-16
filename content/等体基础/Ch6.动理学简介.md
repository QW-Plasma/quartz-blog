# 分布函数

每个粒子都有相空间坐标、速度。引入六维相空间 $(\vec{r},\vec{v})$

一个粒子都有一点与之对应。

$t$ 时刻，空间范围 $(\vec{r},\vec{r}+d\vec{r})$ $(\vec{v}_\alpha,\vec{v}_\alpha+d\vec{v}_\alpha)$ 之间 ，$\alpha$ 类粒子个数

$$
dN_\alpha=f_\alpha(\vec{r},\vec{v}_\alpha,t)\,d\vec{r}\,d\vec{v}_\alpha
$$

$f_\alpha(\vec{r},\vec{v}_\alpha,t)$ 为 $\alpha$ 成分的粒子分布函数

粒子数密度表示粒子在空间中的分布，对速度空间积分

$$
n_\alpha(\vec{r},t)=\int f_\alpha(\vec{r},\vec{v}_\alpha,t)\,d\vec{v}_\alpha
$$

每个 $\alpha$ 类粒子的物理量 $\psi_\alpha=\psi_\alpha(\vec{r},\vec{v}_\alpha,t)$

速度空间平均值

$$
\langle\psi_\alpha\rangle
=\frac{\int \psi_\alpha f_\alpha\,d\vec{v}_\alpha}{\int f_\alpha\,d\vec{v}_\alpha}
=\frac{1}{n_\alpha}\int \psi_\alpha f_\alpha\,d\vec{v}_\alpha
$$

经过 $dt$ 时间

① 没有碰撞项

$$
f_\alpha(\vec{r},\vec{v}_\alpha,t)\,d\vec{r}\,d\vec{v}_\alpha
=
f_\alpha(\vec{r}+\vec{v}_\alpha dt,\ \vec{v}_\alpha+\vec{a}_\alpha dt,\ t+dt)\,d\vec{r}\,d\vec{v}_\alpha
$$

② 有碰撞项

$$
f_\alpha(\vec{r}+\vec{v}_\alpha dt,\ \vec{v}_\alpha+\vec{a}_\alpha dt,\ t+dt)\,d\vec{r}\,d\vec{v}_\alpha
=
f_\alpha(\vec{r},\vec{v}_\alpha,t)\,d\vec{r}\,d\vec{v}_\alpha
+\sum C_{\alpha\beta}(f_\alpha,f_\beta)\,d\vec{r}\,d\vec{v}_\alpha\,dt
$$

$\alpha$ 与 $\beta$ 碰撞引起的净效应

展开：

$$
f_\alpha(\vec{r}+\vec{v}_\alpha dt,\ \vec{v}_\alpha+\vec{a}_\alpha dt,\ t+dt)
\sim
f_\alpha(\vec{r},\vec{v}_\alpha,t)
+\frac{\partial f_\alpha}{\partial t}dt
+\vec{v}_\alpha\cdot\frac{\partial f_\alpha}{\partial \vec{r}}dt
+\vec{a}_\alpha\cdot\frac{\partial f_\alpha}{\partial \vec{v}_\alpha}dt
$$

$$
\frac{\partial f_\alpha}{\partial t}
+\vec{v}_\alpha\cdot\frac{\partial f_\alpha}{\partial \vec{r}}
+\vec{a}_\alpha\cdot\frac{\partial f_\alpha}{\partial \vec{v}_\alpha}
=
\left(\frac{\partial f_\alpha}{\partial t}\right)_{\text{碰}}
$$

$$
\vec{a}_\alpha=\frac{q_\alpha}{m}\left(\vec{E}+\vec{v}_\alpha\times\vec{B}\right)
$$

粒子数守恒

$$
\int C_{ee}\,d\vec{v}_e=\int C_{ii}\,d\vec{v}_i=\int C_{ei}\,d\vec{v}_e=\int C_{ie}\,d\vec{v}_i=0
$$

动量守恒

$$
\int m_e\vec{v}_e\,C_{ee}\,d\vec{v}_e=\int m_i\vec{v}_i\,C_{ii}\,d\vec{v}_i=0
$$

总动量守恒

$$
\int m_e\vec{v}_e\,C_{ei}\,d\vec{v}_e+\int m_i\vec{v}_i\,C_{ie}\,d\vec{v}_i=0
$$

能量守恒

$$
\int \frac12 m_e v_e^2\,C_{ee}\,d\vec{v}_e=\int \frac12 m_i v_i^2\,C_{ii}\,d\vec{v}_i=0
$$

$$
\int \frac12 m_e v_e^2\,C_{ei}\,d\vec{v}_e+\int \frac12 m_i v_i^2\,C_{ie}\,d\vec{v}_i=0
$$

无碰撞 Vlasov 方程

$$
\frac{\partial f}{\partial t}
+\vec{v}\cdot\nabla f
+\frac{q}{m}\left(\vec{E}+\vec{v}\times\vec{B}\right)\cdot\nabla_v f
=0
$$
# 流体方程的推导

$$
\int \psi_\alpha\left[\frac{d f_\alpha}{dt}-\left(\frac{\partial f_\alpha}{\partial t}\right)_c\right]\,d\vec{v}_\alpha=0
$$

分别计算各项对速度空间的积分：

①

$$
\int \psi_\alpha \frac{\partial f_\alpha}{\partial t}\,d\vec{v}_\alpha
=
\frac{\partial}{\partial t}\int \psi_\alpha f_\alpha\,d\vec{v}_\alpha
-\int \frac{\partial\psi_\alpha}{\partial t}f_\alpha\,d\vec{v}_\alpha

$$

$$
=\frac{\partial}{\partial t}\left[n_\alpha\langle\psi_\alpha\rangle\right]
-n_\alpha\left\langle\frac{\partial\psi_\alpha}{\partial t}\right\rangle
$$

②

$$
\int \psi_\alpha\,\vec{v}_\alpha\cdot\nabla f_\alpha\,d\vec{v}_\alpha
=
\nabla\cdot\int \psi_\alpha \vec{v}_\alpha f_\alpha\,d\vec{v}_\alpha
-\int f_\alpha\,\nabla\cdot(\psi_\alpha\vec{v}_\alpha)\,d\vec{v}_\alpha
$$

$$
=
\nabla\cdot\left(n_\alpha\langle\psi_\alpha\vec{v}_\alpha\rangle\right)
-n_\alpha\langle\vec{v}_\alpha\cdot\nabla\psi_\alpha\rangle,
\qquad \nabla\cdot\vec{v}_\alpha=0
$$

③

$$
\int \psi_\alpha\,\vec{a}_\alpha\cdot\nabla_{v} f_\alpha\,d\vec{v}_\alpha
=
\int \nabla_v\cdot(\psi_\alpha \vec{a}_\alpha f_\alpha)\,d\vec{v}_\alpha
-\int \nabla_v\cdot(\psi_\alpha\vec{a}_\alpha)\,f_\alpha\,d\vec{v}_\alpha
$$

$$
=0-\int \left(\vec{a}_\alpha\cdot\nabla_v\psi_\alpha+\psi_\alpha\,\nabla_v\cdot\vec{a}_\alpha\right)f_\alpha\,d\vec{v}_\alpha
=
-n_\alpha\langle\vec{a}_\alpha\cdot\nabla_v\psi_\alpha\rangle \qquad \nabla_{\vec{v}}\cdot(\vec{E}+\vec{v}\times \vec{B})=0
$$

④

$$
\int \psi_\alpha\left(\frac{\partial f_\alpha}{\partial t}\right)_c d\vec{v}_\alpha
=
\sum\int \psi_\alpha C_{\alpha\beta}(f_\alpha,f_\beta)\,d\vec{v}_\alpha
=
\Delta\left(n_\alpha\langle\psi_\alpha\rangle\right)
$$

代入不同的物理量 $\psi_{\alpha}$ 导出双流体方程

$$
\frac{\partial}{\partial t}\left[n_\alpha\langle\psi_\alpha\rangle\right]
-n_\alpha\left\langle\frac{\partial\psi_\alpha}{\partial t}\right\rangle+\nabla\cdot\left(n_\alpha\langle\psi_\alpha\vec{v}_\alpha\rangle\right)
-n_\alpha\langle\vec{v}_\alpha\cdot\nabla\psi_\alpha\rangle
-n_\alpha\langle\vec{a}_\alpha\cdot\nabla_v\psi_\alpha\rangle=\sum\int \psi_\alpha C_{\alpha\beta}(f_\alpha,f_\beta)\,d\vec{v}_\alpha
$$
## 连续性方程

令 $\psi_\alpha=m_\alpha$，$\langle\psi_\alpha\rangle=m_\alpha$，$\langle\psi_\alpha\vec{v}_\alpha\rangle=m_\alpha\vec{u}_\alpha$

$$
\frac{\partial}{\partial t}(n_\alpha m_\alpha)+\nabla\cdot(n_\alpha m_\alpha\vec{u}_\alpha)=0
$$

## 动量方程

粒子无规热运动速度 $\vec{w}_\alpha=\vec{v}_\alpha-\vec{u}_\alpha,\ \langle\vec{w}_\alpha\rangle=0$

$$
\overleftrightarrow{P}_\alpha
=
m_\alpha\int f_\alpha\,\vec{w}_\alpha\vec{w}_\alpha\,d\vec{v}_\alpha
=
\rho_\alpha\langle\vec{w}_\alpha\vec{w}_\alpha\rangle
$$

令 $\psi_\alpha=m_\alpha\vec{v}_\alpha$，$\langle\psi_\alpha\rangle=m_\alpha\vec{u}_\alpha$

$$
\langle\vec{v}_\alpha\vec{v}_\alpha\rangle
=
\langle(\vec{w}_\alpha+\vec{u}_\alpha)(\vec{w}_\alpha+\vec{u}_\alpha)\rangle
=
\langle\vec{w}_\alpha\vec{w}_\alpha\rangle+\vec{u}_\alpha\vec{u}_\alpha
$$

$$
\frac{\partial}{\partial t}\left[n_\alpha\langle\psi_\alpha\rangle\right]
=
\frac{\partial}{\partial t}\left(\rho_\alpha\vec{u}_\alpha\right)
$$

$$
\nabla\cdot\left(n_\alpha\langle\psi_\alpha\vec{v}_\alpha\rangle\right)
=
\nabla\cdot\left(\rho_\alpha\vec{u}_\alpha\vec{u}_\alpha\right)+\nabla\cdot\overleftrightarrow{P}_\alpha
$$

$$
-n_\alpha\langle\vec{a}_\alpha\cdot\nabla_v\psi_\alpha\rangle
=
-n_\alpha\langle\vec{a}_\alpha\cdot m_\alpha\nabla_v\vec{v}_\alpha\rangle
=
-\rho_\alpha\vec{a}_\alpha
$$

合并后再代入连续性方程可以得到熟悉的动量方程

$$
m_\alpha n_\alpha\frac{d\vec{u}_\alpha}{dt}
=
-\nabla\cdot\overleftrightarrow{P}_\alpha
+n_\alpha q_\alpha(\vec{E}+\vec{u}_\alpha\times\vec{B})
+\vec{R}_{\alpha\beta}
$$
## 能量方程

定义热流与温度

$$
\left\{
\begin{aligned}
\vec{q}_\alpha = \frac12 n_\alpha m_\alpha\langle w_\alpha^2\vec{w}_\alpha\rangle \\
\frac32 n_\alpha T_\alpha = n_\alpha\frac12 m_\alpha\langle w_\alpha^2\rangle
\end{aligned}
\right.
$$

$$
\overleftrightarrow{P}_\alpha
=
m_\alpha\int f_\alpha\,\vec{w}_\alpha\vec{w}_\alpha\,d\vec{v}_\alpha
=
\rho_\alpha\langle\vec{w}_\alpha\vec{w}_\alpha\rangle
$$

令 $\psi_\alpha=\frac12 m_\alpha v_\alpha^2$

$$
\frac{\partial}{\partial t}\left[n_\alpha\langle\psi_\alpha\rangle\right]
-n_\alpha\left\langle\frac{\partial\psi_\alpha}{\partial t}\right\rangle+\nabla\cdot\left(n_\alpha\langle\psi_\alpha\vec{v}_\alpha\rangle\right)
-n_\alpha\langle\vec{v}_\alpha\cdot\nabla\psi_\alpha\rangle
-n_\alpha\langle\vec{a}_\alpha\cdot\nabla_v\psi_\alpha\rangle=\sum\int \psi_\alpha C_{\alpha\beta}(f_\alpha,f_\beta)\,d\vec{v}_\alpha
$$

$$
\langle\psi_\alpha\rangle
=\frac12 m_\alpha\langle(\vec{u}_\alpha+\vec{w}_\alpha)^2\rangle
=\frac12 m_\alpha(u_\alpha^2+\langle w_\alpha^2\rangle)
=\frac12 m_\alpha u_\alpha^2+\frac32 T_\alpha
$$

$$
\langle\psi_\alpha\vec{v}_\alpha\rangle
=\frac12 m_\alpha\langle v_\alpha^2\vec{v}_\alpha\rangle
=\frac12 m_{\alpha}\left\langle\left(u_\alpha^2+2\vec{u}_\alpha\cdot\vec{w}_\alpha+w_\alpha^2\right)(\vec{u}_\alpha+\vec{w}_\alpha)\right\rangle
$$

$$
=\frac12 m_\alpha u_\alpha^2\vec{u}_\alpha
+\frac{1}{n_\alpha}\overleftrightarrow{P}_\alpha\cdot\vec{u}_\alpha
+\frac32 T_\alpha\vec{u}_\alpha
+\frac{1}{n_\alpha}\vec{q}_\alpha
$$

$$
\langle\vec{a}_\alpha\cdot\nabla_v\psi_\alpha\rangle
=
\left\langle
\frac{q_\alpha}{m_\alpha}(\vec{E}+\vec{v}_\alpha\times\vec{B})\cdot m_\alpha\vec{v}_\alpha
\right\rangle
=
\langle q_\alpha\vec{E}\cdot\vec{v}_\alpha\rangle
=
q_\alpha\vec{E}\cdot\vec{u}_\alpha
$$

$$
\frac{\partial}{\partial t}\left(\frac12 n_\alpha m_\alpha u_\alpha^2+\frac32 n_\alpha T_\alpha\right)
+\nabla\cdot\left[\frac12 m_\alpha n_\alpha u_\alpha^2\vec{u}_\alpha+\overleftrightarrow{P}_\alpha\cdot\vec{u}_\alpha+\frac32 n_\alpha T_\alpha\vec{u}_\alpha+\vec{q}_\alpha\right]
-n_\alpha q_\alpha\vec{E}\cdot\vec{u}_\alpha
=
\Delta\left(n_\alpha\left\langle\frac12 m_\alpha v_\alpha^2\right\rangle\right)
$$
