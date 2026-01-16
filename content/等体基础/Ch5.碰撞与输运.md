# 等离子体碰撞和输运

碰撞过程：气、液体达到热力学平衡的主要途径

碰撞过程决定系统的弛豫过程（由速度空间的非热力学平衡到热力学平衡的过渡）与输运过程（空间非均匀的局部或热平衡不均匀的过渡）

中性粒子碰撞可用刚性球碰撞来模拟，作用发生在接触瞬间

等离子体包含中性、带电粒子

- 中性粒子之间（两体碰撞）
- 带电粒子之间（库仑力） $\rightarrow$ 长程作用

带电粒子会受到周围很多粒子的库仑力，多体碰撞

- 经典输运（由碰撞引起） $\rightarrow$ 新经典输运（环位形）
- 反常输运（各种由不稳定性引起）

等离子体库仑相互作用分为两部分：

1. $r > \lambda_D$，用自洽场来取代，以某一粒子为中心的德拜球外所有粒子对他的库仑作用表现出一个平均的宏观电场，即自洽场
2. $r < \lambda_D$，库仑相互作用 $\rightarrow$ 大量带电粒子 $\rightarrow$ 多体碰撞 $N_D = \frac{4}{3} \pi \lambda_D^3 \gg 1$

粒子所能接近的最短距离（Landau长度）

$$\rho_L = \frac{e^2}{4\pi \varepsilon_0 T_e}$$

$$\frac{\rho_L}{d} \sim \frac{\rho_L}{n^{-1/3}} \sim (n \lambda_D^3)^{-2/3} \ll 1$$

Landau长度远小于粒子间距，近似用两体碰撞叠加
# 库仑碰撞

考虑两类粒子之间的碰撞

$$\alpha, m_\alpha, \vec{v}_\alpha; \beta, m_\beta, \vec{v}_\beta$$

动量守恒与能量守恒

$$\begin{cases} \vec{P}_\alpha + \vec{P}_\beta = \vec{P}_\alpha' + \vec{P}_\beta' \\ E_{k\alpha} + E_{k\beta} = E_{k\alpha}' + E_{k\beta}' + \Delta E \end{cases}$$

考虑质心系

$$
\begin{cases}
\vec{R}_c = \frac{m_\alpha \vec{r}_\alpha + m_\beta \vec{r}_\beta}{m_\alpha + m_\beta}\\ \\
\vec{v}_c = \dot{\vec{R}}_c
\end{cases}
$$

求相对于质心速度，其他类似

$$
\begin{cases}
\vec{v}_{\alpha c} = \vec{v}_\alpha - \vec{v}_c \\
\vec{v}_{\alpha\beta} = \vec{v}_\alpha - \vec{v}_\beta, \quad \vec{v}_{\alpha\beta}' = \vec{v}_\alpha' - \vec{v}_\beta' \\
\vec{v}_{\alpha c} = \vec{v}_\alpha - \frac{m_\alpha \vec{v}_\alpha + m_\beta \vec{v}_\beta}{m_\alpha + m_\beta} = M_\beta \vec{v}_{\alpha\beta} \\
M_\alpha = \frac{m_\alpha}{m_\alpha + m_\beta}, \quad M_\beta = \frac{m_\beta}{m_\alpha + m_\beta}
\end{cases}
$$

同理

$$\vec{v}_{\beta c} = -M_\alpha \vec{v}_{\alpha\beta}, \vec{v}_{\alpha c}' = M_\beta \vec{v}_{\alpha\beta}', \vec{v}_{\beta c}' = -M_\alpha \vec{v}_{\alpha\beta}'$$

质心系下已自动满足动量守恒，考虑完全弹性碰撞，能量守恒：

$$\frac{1}{2} m_{\alpha\beta} \vec{v}_{\alpha\beta}^2 = \frac{1}{2} m_{\alpha\beta} \vec{v}_{\alpha\beta}'^2 \quad m_{\alpha\beta} = \frac{m_\alpha m_\beta}{m_\alpha + m_\beta}$$

$\alpha$ 粒子碰撞前后动量改变量

$$\Delta \vec{P}_\alpha = m_\alpha (\vec{v}_\alpha' - \vec{v}_\alpha) = m_{\alpha\beta} \Delta \vec{v}_{\alpha\beta} = -\Delta \vec{P}_\beta$$

$$\vec{v}_{\alpha\beta}' = v_{\alpha\beta} (\sin\theta \cos\varphi \vec{e}_1 + \sin\theta \sin\varphi \vec{e}_2 + \cos\theta \vec{e}_3)$$

$$\Delta \vec{v}_{\alpha\beta} = v_{\alpha\beta} (\sin\theta \cos\varphi \vec{e}_1 + \sin\theta \sin\varphi \vec{e}_2 - 2\sin^2 \frac{\theta}{2} \vec{e}_3)$$

对 $\varphi$ 平均

$$\langle \Delta \vec{P}_\alpha \rangle = -2 m_{\alpha\beta} \sin^2 \frac{\theta}{2} \vec{v}_{\alpha\beta}$$
# 卢瑟福散射

$$\tan \frac{\theta}{2} = \frac{b_0}{b}, \quad b_0 = \frac{Z_\alpha Z_\beta e^2}{4\pi \varepsilon_0 m_{\alpha\beta} v_{\alpha\beta}^2}$$

$b$ 为瞄准距离，散射截面，半径为 $b$ 的圆内，流强为 $I = n v_{\alpha\beta}$ 的粒子流被 $\beta$ 粒子散射后落入立体的元 $d\Omega = \sin\theta d\theta d\varphi$ 的粒子数

$$dN = \sigma_{\alpha\beta} n v_{\alpha\beta} d\Omega, \quad \sigma_{\alpha\beta} \text{ 为微分散射截面}$$

$$dN = I b db d\varphi = n v_{\alpha\beta} b db d\varphi$$

$$\sigma_{\alpha\beta} = \frac{b}{\sin\theta} |\frac{db}{d\theta}|$$

对于库伦散射

$$\sigma_{\alpha\beta库} = \frac{b_0^2}{4 \sin^4 \frac{\theta}{2}}$$

动量输运截面

$$\sigma_{\alpha\beta}^m = 2\pi \int (1 - \cos\theta) \sigma_{\alpha\beta} \sin\theta d\theta$$

有效碰撞频率，平均自由程

$$\nu_{\alpha\beta} = n_\beta \sigma_{\alpha\beta}^m v_{\alpha\beta}, \quad \lambda_{\alpha\beta} = \frac{1}{n_\beta \sigma_{\alpha\beta}^m}$$

① 近碰撞 $\frac{\pi}{2} \le \theta \le \pi, \Rightarrow 0 \le b \le \langle b_0 \rangle$

$$\langle b_0 \rangle = \frac{Z_\alpha Z_\beta e^2}{4\pi \varepsilon_0 m_{\alpha\beta} \langle v_{\alpha\beta}^2 \rangle} = \frac{Z_\alpha Z_\beta e^2}{4\pi \varepsilon_0 T} = \lambda_L$$

$$\text{近碰撞截面 } \sigma_{\alpha\beta \text{近}} = \pi \langle b_0 \rangle^2 = \pi \lambda_L^2$$

② 远碰撞 $\theta < \frac{\pi}{2} \Rightarrow b > \langle b_0 \rangle, \quad \langle b_0 \rangle < b \le \lambda_D$

$$\text{远碰撞截面 } \sigma_{\alpha\beta \text{远}} = 2\pi \int_{\langle b_0 \rangle}^{\lambda_D} b db = \pi (\lambda_D^2 - \langle b_0 \rangle^2) \sim \pi \lambda_D^2$$

$$\frac{\sigma_{\alpha\beta \text{远}}}{\sigma_{\alpha\beta \text{近}}} = \frac{\lambda_D^2}{\lambda_L^2} - 1 \sim \Lambda^2$$

$$\Lambda = \frac{\lambda_D}{\lambda_L} \gg 1$$

远碰撞概率要大得多

经过多次小角度散射可以累积成一次大的偏转

等离子体粒子大角度偏转主要是远碰撞累计引起的

一个试探粒子在碰撞中每次偏转是无规性的

多个试探粒子平均后，$\langle \theta \rangle = 0$

$$\langle \theta \rangle = N \langle \Delta \theta_i \rangle = 0$$

$$\langle \theta^2 \rangle = N \langle \Delta \theta_i^2 \rangle + \sum_{i \ne j} \langle \Delta \theta_i \Delta \theta_j \rangle = N \langle \Delta \theta^2 \rangle$$

相当于偏转角度上的无规行走

$\langle \Delta \theta^2 \rangle$ 为具有不同参数试探粒子对一个均粒子的平均

$$\langle \Delta \theta^2 \rangle = \int_{\lambda_L}^{\lambda_D} \Delta \theta^2 2\pi b db / \int_{\lambda_L}^{\lambda_D} 2\pi b db$$

每个试探粒子单位长度碰到的粒子个数

$$N' = n_\beta \int_{\lambda_L}^{\lambda_D} 2\pi b db$$

走过 $\lambda$ 长度的均方偏转

$$\langle \theta^2 \rangle = \lambda N' \langle \Delta \theta^2 \rangle = \lambda n_\beta \int_{\lambda_L}^{\lambda_D} (\frac{2b_0}{b})^2 2\pi b db = \lambda n_\beta 8\pi b_0^2 \ln \frac{\lambda_D}{\lambda_L}$$

发生90度偏转走过的距离

$$\lambda_{\alpha\beta, \text{远}} = \frac{1}{n_\beta 8\pi b_0^2 \ln \Lambda}$$

即远碰撞的有效自由程

$$\sigma_{\alpha\beta, 90^\circ, \text{远}} = \frac{1}{n_\beta \lambda_{\alpha\beta, \text{远}}} = 8\pi b_0^2 \ln \Lambda \gg \sigma_{\alpha\beta \text{近}}$$
# 欧姆加热

考虑简单模型: $\vec{B}_0 = 0, \vec{E} \ne 0$, 离子、电子有影响

物理图像：相对运动增强 $\rightarrow$ 产生电流增强 $\rightarrow$ 库仑碰撞阻碍加速 $\rightarrow$ 达到平衡

$$-n_e e \vec{E} + \vec{R}_{ei} = 0, \quad \vec{R}_{ei} = n_e m_e (\vec{u}_i - \vec{u}_e) \langle \nu_{ei} \rangle$$

$$\vec{E} = \eta \vec{J}, \quad \eta = \frac{m_e \langle \nu_{ei} \rangle}{n_e e^2} = \frac{m_e^{1/2} e^2 \ln \Lambda}{32\sqrt{\pi} \varepsilon_0^2 T_e^{3/2}}, \quad \eta \propto T_e^{-3/2}$$

适用于完全电离的等离子体

欧姆加热，$\vec{J}$ 通过等离子体，由导致焦耳热损失 $\eta J^2$ ，从而加热等离子体

温度不断升高，电阻率下降，加热功率下降，需要引入其他加热手段。

$$T \uparrow \rightarrow \eta \downarrow \rightarrow \text{加热功率} \downarrow$$
# 输运过程的经验定律

处于非平衡态，参量非均匀 $\xrightarrow{\text{碰撞}}$ 粒子迁移，动量迁移，电荷迁移，能量迁移，称为输运过程

- 直观分析法：试探粒子与其它粒子碰撞的运动行为，从而得到直观结论
- 统计方法：动理学理论分析

表征输运强弱 —— 输运系数

## 扩散过程

$n$ 不均匀 $\xrightarrow{\text{碰撞}}$ 均匀，$\nabla n$, 粒子流密度 $\vec{\Gamma}$

$$\vec{\Gamma}_\alpha = -D_\alpha \nabla n_\alpha \text{ （菲克定律） } D_\alpha \text{ 为扩散系数}$$

$$\vec{\Gamma}_\alpha = n_\alpha \langle \vec{v}_\alpha \rangle$$

## 热传导过程

热流密度 $\vec{q}_\alpha = -\kappa_\alpha \nabla T_\alpha$ （Fourier 定律）

$\kappa_\alpha$ 为热传导系数

# 粘滞过程

$$\vec{P}_\alpha = -\eta_\alpha \nabla \vec{u}_\alpha \text{ （牛顿粘滞定律）}$$
# 无磁场中弱电离等离子的输运过程

中性粒子碰撞占主导，$\vec{B}_0 = 0$, 无粘滞，$\nu_{\alpha n}$ 与速度无关

$$m_\alpha (\frac{\partial \vec{u}_\alpha}{\partial t} + \vec{u}_\alpha \cdot \nabla \vec{u}_\alpha) = q_\alpha \vec{E} - \frac{1}{n_\alpha} \nabla (n_\alpha T_\alpha) - m_{\alpha n} \nu_{\alpha n} (\vec{u}_\alpha - \vec{u}_n)$$

参数变化时间 $\tau \nu_{\alpha n} \gg 1, \quad u_n \ll u_\alpha, \quad m_{\alpha n} = \frac{m_\alpha m_n}{m_\alpha + m_n}$

忽略惯性项，稳态时

$$\vec{u}_\alpha = \frac{q_\alpha}{m_{\alpha n} \nu_{\alpha n}} \vec{E} - \frac{T_\alpha}{m_{\alpha n} \nu_{\alpha n}} \frac{\nabla n_\alpha}{n_\alpha} - \frac{1}{m_{\alpha n} \nu_{\alpha n}} \nabla T_\alpha$$

$$\vec{u}_\alpha = \vec{u}_{\alpha E} + \vec{u}_{\alpha n} + \vec{u}_{\alpha T}$$

$$\vec{u}_{\alpha E} = b_\alpha \vec{E}, \quad b_\alpha \text{ 为迁移率}$$

$$\text{迁移流 } \vec{\Gamma}_{\alpha, \text{迁移}} = n_\alpha \vec{u}_{\alpha E} = n_\alpha b_\alpha \vec{E}$$

$$\vec{\Gamma}_{\alpha, \text{扩散}} = n_\alpha \vec{u}_{\alpha n} = -D_\alpha \nabla n_\alpha, \quad D_\alpha = \frac{T_\alpha}{m_{\alpha n} \nu_{\alpha n}}$$

$$\vec{q}_\alpha = n_\alpha T_\alpha \vec{u}_{\alpha T} = -D_\alpha^T \nabla T_\alpha, \quad D_\alpha^T = \frac{T_\alpha}{m_{\alpha n} \nu_{\alpha n}}$$

$$\frac{D_\alpha}{b_\alpha} = \frac{T_\alpha}{q_\alpha} \text{ 爱因斯坦关系，一般情况 } \nu_{\alpha n} \propto m_\alpha^{-1/2}$$

若 $T_e \sim T_i$，则 $|b_e| \gg |b_i|, D_e \gg D_i$，电子迁移和扩散比离子快

弱电离等离子体电导率

$$\vec{J} = e n_i \vec{u}_i - e n_e \vec{u}_e\vec{J} = e n (b_i + |b_e|) \vec{E} = \sigma \vec{E}$$

$$\sigma = \frac{n e^2}{m_e \nu_{en}}$$
# 双极扩散

物理图像：由于电子比离子扩散快 $\rightarrow$ 电荷分离电场 $\rightarrow$ 阻碍电子加速离子 $\rightarrow$ 达到平衡 ($\vec{\Gamma}_e = \vec{\Gamma}_i$)

$$
\begin{cases}
\vec{\Gamma}_e = -D_e \nabla n_e + n_e b_e \vec{E} \\
\vec{\Gamma}_i = -D_i \nabla n_i + n_i b_i \vec{E}
\end{cases}
$$

两者相等时达到稳态

$$\Rightarrow \vec{E}_A = \frac{D_e - D_i}{b_e - b_i} \cdot \frac{\nabla n}{n} \sim -\frac{T_e}{e} \frac{\nabla n}{n} \text{ （双极电场） } = -\nabla \varphi$$

$$\varphi - \varphi_0 = \frac{T_e}{e} \ln \frac{n}{n_0}, \quad n = n_0 \exp(e \frac{\varphi - \varphi_0}{T_e})$$

双极扩散流 $\vec{\Gamma}=\vec{\Gamma}_{e}=\vec{\Gamma}_{i}$

$$\vec{\Gamma} = -\frac{D_e b_i - D_i b_e}{b_e + b_i} \nabla n = -D_A \nabla n, \quad D_A \sim D_i (1 + \frac{T_e}{T_i})$$
# 均匀恒定磁场中弱电离等离子体输运
$$q_\alpha \vec{E} + q_\alpha (\vec{u}_\alpha \times \vec{B}) - \frac{1}{n_\alpha} \nabla (n_\alpha T_\alpha) - m_\alpha \nu_{\alpha \beta} \vec{u}_\alpha = 0$$

平行 $\vec{B}$ 方向：

$$q_\alpha E_\parallel - \frac{1}{n_\alpha} \nabla_\parallel (n_\alpha T_\alpha) - m_\alpha \nu_{\alpha p} u_{\alpha\parallel} = 0$$

$$u_{\alpha\parallel} = b_{\alpha\parallel} E_\parallel - D_{\alpha\parallel} \frac{\nabla_\parallel n_\alpha}{n_\alpha} - D_{\alpha\parallel}^T \frac{\nabla_\parallel T_\alpha}{T_\alpha}$$

垂直 $\vec{B}$ 方向：

$$\begin{cases}
q_\alpha \vec{E}_\perp + q_\alpha (\vec{u}_\alpha \times \vec{B}) - \frac{1}{n_\alpha} \nabla_\perp (n_\alpha T_\alpha) - m_\alpha \nu_{\alpha p} \vec{u}_{\alpha\perp} = 0 \\
q_\alpha \vec{E}_\perp \times \vec{B} - q_\alpha B \vec{u}_{\alpha\perp} - \frac{1}{n_\alpha} \nabla_\perp (n_\alpha T_\alpha) \times \vec{B} - m_\alpha \nu_{\alpha p} \vec{u}_{\alpha\perp} \times \vec{B} = 0
\end{cases}$$

$\Downarrow$

$$
\begin{cases}
m_\alpha \omega_{c\alpha} \vec{u}_{\alpha\perp} \times \vec{b} - m_\alpha \nu_{\alpha n} \vec{u}_{\alpha\perp} = -q_\alpha \vec{E}_\perp + \frac{1}{n_\alpha} \nabla_\perp (n_\alpha T_\alpha) \\
-m_\alpha \omega_{c\alpha} \vec{u}_{\alpha\perp} - m_\alpha \nu_{\alpha n} \vec{u}_{\alpha\perp} \times \vec{b} = -q_\alpha \vec{E}_\perp \times \vec{b} + \frac{1}{n_\alpha} \nabla_\perp (n_\alpha T_\alpha) \times \vec{b}
\end{cases}
$$

$\Downarrow$

$$-m_\alpha (\nu_{\alpha n}^2 + \omega_{c\alpha}^2) \vec{u}_{\alpha\perp} = -\nu_{\alpha n} q_\alpha \vec{E}_\perp + \nu_{\alpha n} \frac{1}{n_\alpha} \nabla_\perp (n_\alpha T_\alpha) - \omega_{c\alpha} q_\alpha \vec{E}_\perp \times \vec{b} + \omega_{c\alpha} \frac{1}{n_\alpha} \nabla_\perp (n_\alpha T_\alpha) \times \vec{b}$$

$\Downarrow$

$$\vec{u}_{\alpha\perp} = \frac{1}{\nu_{\alpha n}^2 + \omega_{c\alpha}^2} \frac{\nu_{\alpha n}}{m_\alpha} (q_\alpha \vec{E}_\perp - \frac{1}{n_\alpha} \nabla_\perp (n_\alpha T_\alpha)) + \frac{1}{\nu_{\alpha n}^2 + \omega_{c\alpha}^2} \frac{\omega_{c\alpha}}{m_\alpha} (q_\alpha \vec{E}_\perp \times \vec{b} - \frac{1}{n_\alpha} \nabla_\perp (n_\alpha T_\alpha) \times \vec{b})$$

$$\vec{u}_{\alpha\perp} = \vec{u}_{\alpha te} + \vec{u}_{\alpha tp} + \frac{1}{1 + \nu_{\alpha n}^2/\omega_{c\alpha}^2} (\frac{\vec{E}_\perp \times \vec{b}}{B} + \frac{1}{n_\alpha q_\alpha B} \vec{b} \times \nabla_\perp (n_\alpha T_\alpha))$$

- 当 $\nu_{\alpha n}^2/\omega_{c\alpha}^2 \gg 1$，碰撞使回旋运动无法完成一个完整周期

$$\frac{1}{1 + \nu_{\alpha n}^2/\omega_{c\alpha}^2} = \frac{\omega_{c\alpha}^2}{\nu_{\alpha n}^2}$$

- 当 $\nu_{\alpha n}^2/\omega_{c\alpha}^2 \ll 1$，回旋运动完整，退化为流体漂移

$$\frac{1}{1 + \nu_{\alpha n}^2/\omega_{c\alpha}^2} \sim 1$$

$$\vec{u}_{\alpha te} = b_{\alpha\perp} \vec{E}_\perp, \quad \vec{u}_{\alpha tp} = -D_{\alpha\perp} \frac{\nabla_\perp n_\alpha}{n_\alpha} - D_{\alpha\perp}^T \frac{\nabla_\perp T_\alpha}{T_\alpha}$$

当 $\nu_{\alpha n} \ll \omega_{c\alpha}$，强磁场

$$b_{\alpha\perp} = \frac{\nu_{\alpha n}}{m_\alpha \omega_{c\alpha}^2} q_\alpha = \frac{m_\alpha \nu_{\alpha n}}{q_\alpha B^2} \propto \frac{1}{B^2}$$

$$D_{\alpha\perp} = D_{\alpha\perp}^T = \frac{m_\alpha T_\alpha \nu_{\alpha n}}{q_\alpha^2 B^2} = \frac{v_{th\alpha}^2}{\omega_{c\alpha}^2} \nu_{\alpha n} = \frac{r_{c\alpha}^2}{\tau_{\alpha n}} $$

$$b_{\alpha\perp} / b_{\alpha\parallel} = \nu_{\alpha n}^2 / \omega_{c\alpha}^2 = D_{\alpha\perp} / D_{\alpha\parallel} \ll 1$$

横向输运远小于纵向输运，体现了磁场的约束作用。
