# 流体力学

流体宏观模型：无数流体元的组成

流体元：
$$\begin{cases} \text{宏观无限小} \\ \text{微观无限大} \end{cases}$$

易流动性、粘性、压缩性

① Lagrange 法（随体法）

研究个别流体元 $\vec{r}(t, \vec{\xi})$，$\vec{\xi} = (a, b, c)$
$$\vec{r} = \vec{r}(t, a, b, c), \quad \vec{u} = \frac{\partial}{\partial t} \vec{r}, \quad \vec{a} = \frac{\partial^2}{\partial t^2} \vec{r}$$

② Euler 法（当地法）

场的观点 $\vec{u} = \vec{u}(t, \vec{r})$

$\vec{r}$ 处，$\frac{\partial \vec{u}}{\partial t}$

$t$ 时刻，$\frac{d\vec{r}}{dt} \cdot \frac{\partial \vec{u}}{\partial \vec{r}}$

$$\frac{d}{dt} = \frac{\partial}{\partial t} + \vec{u} \cdot \nabla$$

$$\frac{d\vec{u}}{dt} = \frac{\partial \vec{u}}{\partial t} + \vec{u} \cdot \nabla \vec{u}$$

应力：体积力、表面力（法、切）
$$\vec{p} = \frac{d\vec{f}}{d\sigma}$$

应力与受力面取向有关，两个矢量的函数

可表示为法线矢量与张量的乘积
$$\vec{p}_n d\vec{\sigma_n} = \vec{p}_x d\vec{\sigma_n} \cdot \vec{e}_x + \vec{p}_y d\vec{\sigma_n} \cdot \vec{e}_y + \vec{p}_z d\vec{\sigma_n} \cdot \vec{e}_z$$

$$\vec{p}_n = \alpha \vec{p}_x + \beta \vec{p}_y + \gamma \vec{p}_z$$

$\alpha = \frac{d\vec{\sigma_n} \cdot \vec{e}_x}{d\sigma_n}$ 方向余弦

$$\begin{cases} p_{nx} = \alpha p_{xx} + \beta p_{yx} + \gamma p_{zx} \\ p_{ny} = \alpha p_{xy} + \beta p_{yy} + \gamma p_{zy} \\ p_{nz} = \alpha p_{xz} + \beta p_{yz} + \gamma p_{zz} \end{cases}$$

应力张量 $\overleftrightarrow{P}$

$$\overleftrightarrow{P} = \begin{pmatrix} p_{xx} & p_{yx} & p_{zx} \\ p_{xy} & p_{yy} & p_{zy} \\ p_{xz} & p_{yz} & p_{zz} \end{pmatrix}, \quad \vec{p}_n = \vec{e}_n \cdot \overleftrightarrow{P}$$

理想流体 各向同性
$$\overleftrightarrow{P} = -p \overleftrightarrow{I}$$
# 流体基本方程

1.连续性方程（质量守恒）

$\int_\tau \rho d\tau$ 守恒
$$\int_\Sigma \rho \vec{u} \cdot d\vec{\sigma} = -\frac{\partial}{\partial t} \int_\tau \rho d\tau = \int_\tau \nabla \cdot (\rho \vec{u}) d\tau$$

$$\Rightarrow \frac{\partial}{\partial t} \rho + \nabla \cdot (\rho \vec{u}) = 0$$

或者
$$\frac{d\rho}{dt} + \rho \nabla \cdot \vec{u} = 0$$

不可压缩 $\frac{d\rho}{dt} = 0 \Rightarrow \nabla \cdot \vec{u} = 0$

2.运动方程（动量守恒）
$$\int_\tau \rho \left( \frac{d\vec{u}}{dt} \right) d\tau = \int_\tau \rho \vec{g} d\tau + \int_\Sigma \vec{p}_n d\sigma$$

$$\rho \frac{d\vec{u}}{dt} = \nabla \cdot \overleftrightarrow{P} + \rho \vec{g}$$

3.能量方程（能量守恒）
$$\frac{d}{dt} \int_\tau \rho (\varepsilon + \frac{u^2}{2}) d\tau = \int_\tau \rho \vec{g} \cdot \vec{u} d\tau + \int_\Sigma \vec{p}_n \cdot \vec{u} d\sigma-\int_\Sigma \vec{q} \cdot d\vec{\sigma}$$

$$\rho \frac{d}{dt} (\varepsilon + \frac{u^2}{2}) = \nabla \cdot (\overleftrightarrow{P} \cdot \vec{u}) + \rho \vec{g} \cdot \vec{u} - \nabla \cdot \vec{q}$$
# MHD 方程

Maxwell 方程组 + MHD 方程组构成的自洽理论

$$\begin{cases} \nabla \times \vec{E} = -\frac{\partial \vec{B}}{\partial t} \\ \nabla \times \vec{B} = \mu_0 \vec{J} + \mu_0 \varepsilon_0 \frac{\partial \vec{E}}{\partial t} \\ \nabla \cdot \vec{E} = \frac{\rho_q}{\varepsilon_0} \\ \nabla \cdot \vec{B} = 0 \end{cases} \quad \begin{cases} \vec{J} = \sigma \vec{E} \quad (\text{介质静止}) \\ \vec{f} = \rho_q \vec{E} + \vec{J} \times \vec{B} \end{cases}$$

介质以 $\vec{u}$ 运动

$$\begin{cases} \vec{J}' = \sigma \vec{E}' \\ \vec{E}' = \vec{E} + \vec{u} \times \vec{B} \end{cases} \quad \begin{cases} \vec{J}' = \rho_q (\vec{v} - \vec{u}) = \vec{J} - \rho_q \vec{u} \\ \vec{J} = \vec{J}' + \rho_q \vec{u} = \sigma (\vec{E} + \vec{u} \times \vec{B}) + \rho_q \vec{u} \end{cases}$$

传导电流 + 感应电流 + 运流电流

在 MHD 中，等离子体看作良导体，运流电流 $\ll$ 传导电流

场频率为 $\omega$，$\lambda \sim \frac{c}{\omega}$ 远大于流体运动特征长度 $L$

良导体 $\frac{\sigma}{\varepsilon_0 \omega} \gg 1$ 低频电磁波

$$\left| \frac{\mu_0 \varepsilon_0 \frac{\partial \vec{E}}{\partial t}}{\nabla \times \vec{B}} \right| \sim \left| \frac{\frac{1}{c^2} \omega E}{\frac{1}{\omega} \cdot \frac{1}{L^2} E} \right| \sim \frac{\omega^2 L^2}{c^2} \sim \frac{v^2}{c^2} \ll 1$$

$$\left| \frac{\rho_q \vec{u}}{\vec{J}} \right| \sim \left| \frac{(\varepsilon_0 \nabla \cdot \vec{E}) \vec{u}}{\nabla \times \vec{B} / \mu_0} \right| \sim \left| \frac{\mu_0 \varepsilon_0 u E}{B} \right| \sim \left| \frac{\frac{u}{c^2} E}{\frac{1}{L \omega} E} \right| \sim \frac{v^2}{c^2} \ll 1$$

$$\left| \frac{\rho_q \vec{E}}{\vec{J} \times \vec{B}} \right| \sim \left| \frac{\varepsilon_0 \nabla \cdot \vec{E} \vec{E}}{\nabla \times \vec{B} \cdot \vec{B} / \mu_0} \right| = \left| \frac{\frac{1}{c^2} \cdot \frac{1}{L} E^2}{\frac{1}{\omega L} E \cdot \frac{1}{\omega L} E} \right| = \left| \frac{\omega^2 L^2}{c^2} \right| \sim \frac{v^2}{c^2} \ll 1$$

简化为描述低频的 Maxwell 方程

$$\begin{cases} \nabla \times \vec{E} = -\frac{\partial}{\partial t} \vec{B} \\ \nabla \times \vec{B} = \mu_0 \vec{J} \\ \nabla \cdot \vec{E} = \frac{\rho_q}{\varepsilon_0} \\ \nabla \cdot \vec{B} = 0 \end{cases} \quad \begin{cases} \vec{J} = \sigma (\vec{E} + \vec{u} \times \vec{B}) \\ \vec{f} = \vec{J} \times \vec{B} \end{cases}$$

连续性方程：

$$\frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \vec{u}) = 0$$

运动方程：

$$\rho \frac{d\vec{u}}{dt} = \nabla \cdot \overleftrightarrow{P} + \vec{J} \times \vec{B}$$

无粘情况 $\nabla \cdot \overleftrightarrow{P} = -\nabla p$

$$\rho \frac{d\vec{u}}{dt} = -\nabla p + \vec{J} \times \vec{B}$$

能量方程：

$$\rho \frac{d}{dt} (\varepsilon + \frac{u^2}{2}) = \nabla \cdot (\overleftrightarrow{P} \cdot \vec{u}) + \vec{J} \cdot \vec{E} - \nabla \cdot \vec{q}$$

状态方程：

$$\begin{cases} \text{等温 } \frac{d}{dt} (\frac{p}{\rho}) = 0 \quad \gamma = C_p / C_v \\ \text{绝热 } \frac{d}{dt} (p \rho^{-\gamma}) = 0 \end{cases}$$
# MHD

$$\begin{cases} \frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \vec{u}) = 0 \\ \rho \frac{d\vec{u}}{dt} = -\nabla p + \vec{J} \times \vec{B} \\ \rho \frac{d}{dt} (\varepsilon + \frac{u^2}{2}) = -\nabla \cdot (p \vec{u}) + \vec{J} \cdot \vec{E} - \nabla \cdot \vec{q} \end{cases} \quad \begin{matrix} \frac{d}{dt} (p \rho^{-\gamma}) = 0 \text{ 代替能量方程} \\\text{以封闭方程组} \end{matrix}$$

低频 Maxwell

$$\begin{cases} \nabla \times \vec{B} = \mu_0 \vec{J} \\ \nabla \times \vec{E} = -\frac{\partial}{\partial t} \vec{B} \\ \nabla \cdot \vec{B} = 0 \\ \nabla \cdot \vec{E} = \frac{\rho_q}{\varepsilon_0} \rightarrow \nabla \cdot \vec{E} = 0 \end{cases} \quad \begin{matrix} \vec{J} = \sigma (\vec{E} + \vec{u} \times \vec{B}) \end{matrix}$$

ideal MHD $\sigma \rightarrow \infty \Rightarrow \vec{E} + \vec{u} \times \vec{B} = 0$
# double MHD

电子与离子分别达到局域热力学平衡

$$\frac{\partial}{\partial t} n_\alpha + \nabla \cdot (n_\alpha \vec{u}_\alpha) = 0$$

$$m_\alpha n_\alpha \frac{d\vec{u}_\alpha}{dt} = -\nabla p_\alpha + n_\alpha q_\alpha (\vec{E} + \vec{u}_\alpha \times \vec{B}) + \vec{R}_{\alpha\beta}$$

$$\nabla \cdot \vec{B} = \mu_0 \vec{J} + \mu_0 \varepsilon_0 \frac{\partial \vec{E}}{\partial t}$$

$$\nabla \cdot \vec{E} = \frac{\rho_q}{\varepsilon_0} = \frac{1}{\varepsilon_0} (n_i z_i e - n_e e)$$

$$\vec{u} = \frac{m_i \vec{u}_i + m_e \vec{u}_e}{m_i + m_e}，n = n_i = n_e$$ 准中性

$$\downarrow \frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \vec{u}) = 0$$

$$n_i m_i \frac{d\vec{u}_i}{dt} + n_e m_e \frac{d\vec{u}_e}{dt} = n (m_i + m_e) \frac{d}{dt} \vec{u} = \rho \frac{d\vec{u}}{dt}$$

退化为MHD方程

# 广义欧姆定律

考虑电子与离子的动量方程

$$
\begin{aligned}
\frac{\partial}{\partial t}(n_e m_e \vec{u}_e) + \nabla \cdot (n_e m_e \vec{u}_e \vec{u}_e) = -\nabla \cdot \vec{P}_e - e n_e (\vec{E} + \vec{u}_e \times \vec{B}) + \vec{R}_e \\
\frac{\partial}{\partial t}(n_i m_i \vec{u}_i) + \nabla \cdot (n_i m_i \vec{u}_i \vec{u}_i) = -\nabla \cdot \vec{P}_i + e n_i (\vec{E} + \vec{u}_i \times \vec{B}) + \vec{R}_i
\end{aligned}
$$

粒子方程乘 $\frac{m_{e}}{m_{i}}$ 减去电子方程得

$$
\begin{aligned}
m_e \frac{\partial}{\partial t}(n_i \vec{u}_i - n_e \vec{u}_e) + m_e \nabla \cdot (n_i \vec{u}_i \vec{u}_i - n_e \vec{u}_e \vec{u}_e) &= \nabla \cdot (\vec{P}_e - \frac{m_e}{m_i} \vec{P}_i) + e [(n_e + \frac{m_e}{m_i} n_i) \vec{E}
+ (n_e \vec{u}_e + \frac{m_e}{m_i} n_i \vec{u}_i) \times \vec{B}] - (\vec{R}_e - \frac{m_e}{m_i} \vec{R}_i)
\end{aligned}
$$

略去小量

$$
\frac{m_e}{e} \frac{\partial \vec{J}}{\partial t} + m_e \nabla \cdot [n (\vec{u}_i \vec{u}_i - \vec{u}_e \vec{u}_e)] = \nabla \cdot \vec{P}_e + n e (\vec{E} + \vec{u}_e \times \vec{B}) - \vec{R}_e
$$

代入碰撞项 $\vec{u}_e = \vec{u}_i - \frac{\vec{J}}{n e} \approx \vec{u} - \frac{\vec{J}}{n e}$，$\vec{R}_e = n m_e \nu_c (\vec{u}_i - \vec{u}_e) = \frac{\nu_c m_e}{e} \vec{J}$

$$
\underbrace{\vec{E}}_{①}
+
\underbrace{\vec{u}\times\vec{B}}_{②}
=
\underbrace{\eta\vec{J}}_{③}
+
\underbrace{\frac{1}{ne}\vec{J}\times\vec{B}}_{④}
-
\underbrace{\frac{1}{ne}\nabla\cdot\vec{P}_e}_{⑤}
+
\underbrace{\frac{m_e}{ne^2}
\left[
\frac{\partial\vec{J}}{\partial t}
+
\nabla\cdot\left(
\vec{u}\vec{J}
+
\vec{J}\vec{u}
-
\frac{\vec{J}\vec{J}}{ne}
\right)
\right]}_{⑥}
$$

下面分别对各项作量级比较，

特征长度 $L$，特征频率 $\omega$，特征速度  $U=L\omega$

定义离子惯性长度与电子惯性长度以及阿尔芬速度

$$
d_{i}=\frac{c}{\omega_{pi}}=\sqrt{ \frac{m_{i}}{\mu_{0}ne^{2}} },d_{e}=\frac{c}{\omega_{pe}}=\sqrt{ \frac{m_{e}}{\mu_{0}ne^{2}} },v_{A}=\frac{B}{\sqrt{ \mu_{0}nm_{i} }}
$$
得到各项之间的量级
$$
\begin{aligned}
\frac{\text{①}}{\text{②}} &\sim \frac{E}{U B}\sim \frac{L\omega B}{U B}\sim O(1),\\[4pt]
\frac{\text{③}}{\text{②}} &\sim \frac{\eta J}{U B}\sim \frac{\eta\left(\frac{1}{\mu_0}\frac{B}{L}\right)}{U B}\sim \frac{\eta}{\mu_0 L U}\sim \frac{\lambda_\eta}{L},\\[4pt]
\frac{\text{④}}{\text{②}} &\sim \frac{\frac{1}{ne}JB}{U B}\sim \frac{J}{neU}\sim \frac{B}{\mu_0 n e L U}\sim \frac{V_A d_i}{U L}\sim \frac{d_i}{L},\\[4pt]
\frac{\text{⑤}}{\text{②}} &\sim \frac{\frac{1}{ne}\nabla(nT_e)}{U B}\sim \frac{T_e}{L e U B}\sim \frac{m_e v_{\mathrm{th},e}^2}{L e U B}\sim \frac{v_{\mathrm{th},e}^2}{L U \omega_{ce}}
\sim \frac{\rho_e}{L}\frac{v_{\mathrm{th},e}}{U}\sim \frac{\rho_e}{L}\frac{v_{\mathrm{th},e}}{V_A},\\[4pt]
\frac{\text{⑥}}{\text{②}} &\sim \frac{\frac{m_e}{n e^2}\omega J}{U B}\sim \frac{m_e\omega\left(\frac{1}{\mu_0}\frac{B}{L}\right)}{n e^2 U B}\sim \frac{m_e\omega}{\mu_0 n e^2 U L}\sim \frac{d_e^2\omega}{U L}\sim \frac{d_e^2}{L^2}.
\end{aligned}
$$
# 磁压力与张力

$$\rho \frac{d\vec{u}}{dt} = -\nabla p + \vec{J} \times \vec{B}$$

$$\vec{J} \times \vec{B} = \frac{1}{\mu_0} (\nabla \times \vec{B}) \times \vec{B} = \frac{1}{\mu_0} (\vec{B} \cdot \nabla \vec{B} - \frac{\nabla B^2}{2})$$

$$= \frac{1}{\mu_0} [\nabla \cdot (\vec{B} \vec{B}) - \nabla \cdot (\frac{B^2}{2} \overleftrightarrow{I})]$$

$$= \frac{1}{\mu_0} \nabla \cdot (\vec{B} \vec{B} - \frac{B^2}{2} \overleftrightarrow{I})$$

磁应力张量

$$\overleftrightarrow{T} = \frac{1}{\mu_0} (\vec{B} \vec{B} - \frac{B^2}{2} \overleftrightarrow{I})$$

$$\vec{F} = \vec{J} \times \vec{B} = \nabla \cdot \overleftrightarrow{T}$$

$$\vec{F} = \int_\tau \nabla \cdot \overleftrightarrow{T} d\tau = \int_\Sigma \vec{e}_n \cdot \overleftrightarrow{T} d\vec{\sigma_n} = \int_\Sigma \vec{T}_n d\sigma$$

$$\vec{T}_n = \frac{1}{\mu_0} [\vec{B} \vec{B} \cdot \vec{e}_n - \frac{1}{2} B^2 \vec{e}_n]$$

分别对应磁张力与磁压力
# 磁扩散与磁冻结

$$\frac{\partial \vec{B}}{\partial t} = -\nabla \times \vec{E} \quad (\eta = const)$$

$$\vec{E} + \vec{u} \times \vec{B} = \eta \vec{J} \quad \rightarrow \frac{\partial \vec{B}}{\partial t} = \nabla \times (\vec{u} \times \vec{B}) - \nabla \times (\eta \vec{J})$$

$$= \nabla \times (\vec{u} \times \vec{B}) - \eta \nabla \times (\frac{1}{\mu_0} \nabla \times \vec{B})$$

$$= \nabla \times (\vec{u} \times \vec{B}) + \frac{\eta}{\mu_0} \nabla^2 \vec{B} (磁感应方程)$$

$\eta_m = \frac{\eta}{\mu_0}$（磁粘滞系数） ，上面分别为对流项和磁扩散项

$$\left| \frac{\nabla \times (\vec{u} \times \vec{B})}{\eta_m \nabla^2 \vec{B}} \right| \sim \left| \frac{\frac{1}{L} u B}{\eta_m \frac{1}{L^2} B} \right| \sim \frac{u L}{\eta_m} = R_m \text{（磁雷诺数）}$$
## 忽略对流项

$$R_m \ll 1 ， \frac{\partial \vec{B}}{\partial t} = \eta_m \nabla^2 \vec{B}$$

磁场扩散 $L_m$ 所需时间 $\tau_m$

$$\frac{B}{\tau_m} \sim \frac{\eta_m}{L_m^2} B$$

$\tau_m = \frac{L_m^2}{\eta_m} = \mu_0 \sigma L_m^2$ ， $\tau \ll \tau_m$ 可视为 ideal MHD

总磁能

$$W_m = \int \frac{1}{2\mu_0} B^2 d\tau$$

$$\frac{\partial}{\partial t} W_m = \frac{1}{\mu_0} \int \vec{B} \cdot \frac{\partial \vec{B}}{\partial t} d\tau$$

$$\vec{B} \cdot \frac{\partial \vec{B}}{\partial t} = \vec{B} \cdot \eta_m \nabla^2 \vec{B} = -\eta_m \mu_0 \vec{B} \cdot \nabla \times \vec{J}$$

$$= -\mu_0 \eta_m [\nabla \cdot (\vec{J} \times \vec{B}) + (\nabla \times \vec{B}) \cdot \vec{J}]$$

$$= -\mu_0 \eta_m \nabla \cdot (\vec{J} \times \vec{B}) - \eta_m \vec{J}^2 \mu_0$$

$$\frac{\partial}{\partial t} W_m = -\eta_m \int_\Sigma \vec{J} \times \vec{B} \cdot d\vec{\sigma} - \mu_0 \eta_m \int_\tau J^2 d\tau$$

$$= -\eta \int_\tau J^2 d\tau \quad \text{ohm 加热}$$
## 忽略扩散项

$$R_m \gg 1 ， \frac{\partial \vec{B}}{\partial t} = \nabla \times (\vec{u} \times \vec{B})，磁力线粘附于流体元上$$

类似无粘不可压流体涡旋方程

$$\frac{\partial \vec{\omega}}{\partial t} = \nabla \times (\vec{u} \times \vec{\omega}) \quad \text{涡旋粘附于流体元上}$$

$\Sigma = \Sigma_1 + \Sigma_2 + \Sigma_3$

$$\oint_\Sigma \vec{B} \cdot d\vec{\sigma} = 0$$

$$-\int_{\Sigma_1} \vec{B}(t_1) \cdot d\vec{\sigma} + \int_{\Sigma_2} \vec{B}(t_1) \cdot d\vec{\sigma} + \int_{\Sigma_3} \vec{B}(t_1) \cdot d\vec{\sigma} = 0$$

$$\int_\Sigma \frac{\partial \vec{B}}{\partial t} \cdot d\vec{\sigma} = \int_\Sigma \nabla \times (\vec{u} \times \vec{B}) \cdot d\vec{\sigma}$$

通过流体元磁通量不变

$$\frac{d}{dt} \Phi = \frac{d}{dt} \int_\Sigma \vec{B} \cdot d\vec{\sigma} = \lim_{\Delta t \rightarrow 0} [\int_{\Sigma_3} \vec{B}(t_2) \cdot d\vec{\sigma} - \int_{\Sigma_1} \vec{B}(t_1) \cdot d\vec{\sigma}] / \Delta t$$

$$= \lim_{\Delta t \rightarrow 0} \frac{1}{\Delta t} [\int_{\Sigma_1} (\vec{B}(t_2) - \vec{B}(t_1)) \cdot d\vec{\sigma} - \int_{\Sigma_2} \vec{B}(t_2) \cdot d\vec{\sigma}]$$

$$= \int_{\Sigma_1} \frac{\partial \vec{B}}{\partial t} \cdot d\vec{\sigma} - \lim_{\Delta t \rightarrow 0} \oint_{C_1} \vec{B}(t_2) \cdot d\vec{l} \times \vec{u} \Delta t / \Delta t$$

$$= \int_{\Sigma_1} \frac{\partial \vec{B}}{\partial t} \cdot d\vec{\sigma} - \oint_{C_1} \vec{u} \times \vec{B} \cdot d\vec{l}$$

$$= \int_{\Sigma_1} [\frac{\partial \vec{B}}{\partial t} - \nabla \times (\vec{u} \times \vec{B})] \cdot d\vec{\sigma} = 0$$

任意磁场可以用 2 个标量场表示

$$\vec{B} = \nabla \alpha \times \nabla \beta \quad \text{2 个曲面的交界线}$$

$$\frac{\partial}{\partial t} (\nabla \alpha \times \nabla \beta) = \nabla \times (\vec{u} \times (\nabla \alpha \times \nabla \beta))$$

$$\nabla \frac{\partial \alpha}{\partial t} \times \nabla \beta + \nabla \alpha \times \nabla \frac{\partial \beta}{\partial t} = \nabla \times (\nabla \alpha \vec{u} \cdot \nabla \beta - \nabla \beta \vec{u} \cdot \nabla \alpha)$$

$$\nabla \times (\frac{\partial \alpha}{\partial t} \nabla \beta - \frac{\partial \beta}{\partial t} \nabla \alpha) = \nabla \times (\nabla \alpha \vec{u} \cdot \nabla \beta - \nabla \beta \vec{u} \cdot \nabla \alpha)$$

$$\nabla \times ((\frac{\partial \alpha}{\partial t} + \vec{u} \cdot \nabla \alpha) \nabla \beta - (\frac{\partial \beta}{\partial t} + \vec{u} \cdot \nabla \beta) \nabla \alpha) = 0$$

$$\frac{d\alpha}{dt} \nabla \beta - \frac{d\beta}{dt} \nabla \alpha = \nabla \psi \quad \psi \text{ 为任意标量场}$$

特殊情况 $\psi = 0 \Rightarrow \frac{d\alpha}{dt} = 0, \frac{d\beta}{dt} = 0$

表示标量场随流体元一起运动 $\rightarrow$ 磁力线也是

$$\nabla \psi \neq 0, \quad \nabla \psi = \frac{\partial \psi}{\partial \alpha} \nabla \alpha + \frac{\partial \psi}{\partial \beta} \nabla \beta$$

$$\frac{d\alpha}{dt} \nabla \beta - \frac{d\beta}{dt} \nabla \alpha = \frac{\partial \psi}{\partial \alpha} \nabla \alpha + \frac{\partial \psi}{\partial \beta} \nabla \beta$$

$$\begin{cases} \frac{d\alpha}{dt} = \frac{\partial \psi}{\partial \beta} \\ \frac{d\beta}{dt} = -\frac{\partial \psi}{\partial \alpha} \end{cases} \quad \psi \text{ 相当于 } (\alpha, \beta) \text{ 的哈密顿量}$$

只能说磁场拓扑结构和流体相同，磁场不会断开

# 流体漂移
## 静止电磁场

$$n_\alpha m_\alpha (\frac{\partial \vec{u}_\alpha}{\partial t} + \vec{u}_\alpha \cdot \nabla \vec{u}_\alpha) = -\nabla p_\alpha + n_\alpha q_\alpha (\vec{E} + \vec{u}_\alpha \times \vec{B})$$

不考虑非线性项，处于稳态平衡时

$$-\nabla p_\alpha + n_\alpha q_\alpha (\vec{E} + \vec{u}_\alpha \times \vec{B}) = 0$$

$$-\frac{\nabla p_\alpha \times \vec{B}}{n_\alpha q_\alpha} = \vec{E} \times \vec{B} + (\vec{u}_\alpha \times \vec{B}) \times \vec{B}$$

$$\frac{\nabla p_\alpha \times \vec{B}}{n_\alpha q_\alpha} = \vec{E} \times \vec{B} - B^2 \vec{u}_{\alpha\perp} \rightarrow \vec{u}_{\alpha\perp} = \frac{\vec{E} \times \vec{B}}{B^2} + \frac{\vec{B} \times \nabla p_\alpha}{n_\alpha q_\alpha B^2}$$

分别为电漂移与抗磁漂移。

物理图像：由于压强梯度存在粒子数梯度，粒子在磁场中做回旋运动，沿着某个方向的粒子数更多，从而带来抗磁漂移电流。

$$\vec{J}_D = \sum n_\alpha q_\alpha \vec{u}_{\alpha\perp} = \frac{\vec{B} \times \nabla (p_i - p_e)}{B^2}$$
## 缓变电场

考虑电场随时间缓慢变化，与单粒子图像一致，此时应该多出极化漂移项 $\vec{u_{p}}$

设总的漂移速度为 $\vec{u_{E}}+\vec{u_P}+\vec{u_{p}}$ ，代入动量方程

$$
m_\alpha n_\alpha
\frac{\partial}{\partial t}
\left[
\frac{\vec{B}\times\nabla p_\alpha}{n_\alpha q_\alpha B^2}
+
\frac{\vec{E}\times\vec{B}}{B^2}
+
\vec{u}_p
\right]
=
-\nabla p_\alpha
+
n_\alpha q_\alpha \vec{E}
+
n_\alpha q_\alpha
\left[
\frac{\vec{B}\times\nabla p_\alpha}{n_\alpha q_\alpha B^2}
+
\frac{\vec{E}\times\vec{B}}{B^2}
+
\vec{u}_p
\right]
\times\vec{B}
$$

右边可以继续化简得

$$
m_\alpha n_\alpha
\frac{\partial}{\partial t}
\left[
\frac{\vec{B}\times\nabla p_\alpha}{n_\alpha q_\alpha B^2}
+
\frac{\vec{E}\times\vec{B}}{B^2}
+
\vec{u}_p
\right]
=n_{\alpha}q_{\alpha}\vec{u_{p}}\times \vec{B}
$$

左边极化漂移项与后边作量级比较，并根据缓变条件

$$
\frac{m_{\alpha}n_{\alpha}\frac{\partial}{\partial t} \vec{u_{p}}}{n_{\alpha}q_{\alpha} \vec{u_{p}} \times \vec{B}} \sim \frac{m_{\alpha}n_{\alpha}\omega u_{p}}{n_{\alpha}q_{\alpha}u_{\alpha}B}\sim \frac{\omega}{\omega_{c\alpha}} \ll 1
$$

得到

$$
m_\alpha n_\alpha
\frac{\partial}{\partial t}
\left[
\frac{\vec{B}\times\nabla p_\alpha}{n_\alpha q_\alpha B^2}+\frac{\vec{E}\times\vec{B}}{B^2}
\right]
=n_{\alpha}q_{\alpha}\vec{u_{p}}\times \vec{B}
$$

两边同时叉乘 $\vec{B}$ 得到

$$
\vec{u_{\alpha}}=\frac{1}{\omega_{c}B}\frac{\partial}{\partial t} \vec{E}
$$

此时流体中存在的三种漂移：电漂移 抗磁漂移 极化漂移，都与单粒子图像对应。
