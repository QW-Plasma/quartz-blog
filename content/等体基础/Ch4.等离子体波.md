# 波动的基本概念

## 波的表示法，Fourier 分析

$$
\begin{gathered}
f(\vec{r}, t) = \sum_{\omega, \vec{k}} \bar{f} \exp[i(\vec{k} \cdot \vec{r} - \omega t)] \\
k = \frac{2\pi}{\lambda}
\end{gathered}
$$

### 相速度：常相位点的传播速度

$$
\begin{gathered}
\frac{d}{dt} (\vec{k} \cdot \vec{r} - \omega t) = 0 \\
\vec{k} \cdot \vec{v}_p - \omega = 0 \\
\vec{v}_p = \frac{d\vec{r}}{dt} \text{（相速度）}
\end{gathered}
$$

### 波包：由许多单色波（谐波分量）组成的在传播过程中随时间、空间缓变的局域波群。此波包的整体速度为群速度

$$
\begin{gathered}
\vec{E} = \sum_{\vec{k}, \omega} \vec{E}_{\vec{k}, \omega} \exp(i\vec{k} \cdot \vec{r} - i\omega t) \\
\begin{cases} 
E_1 = E_0 \cos[(k + \Delta k)x - (\omega + \Delta \omega)t] \\ 
E_2 = E_0 \cos[(k - \Delta k)x - (\omega - \Delta \omega)t] 
\end{cases} \\
E_1 + E_2 = 2 E_0 \cos(\Delta k x - \Delta \omega t) \cos(kx - \omega t)
\end{gathered}
$$

$2 E_0 \cos(\Delta k x - \Delta \omega t)$ 为包络线，$\Delta k \rightarrow 0$，群速度

$$
\begin{gathered}
v_g = \frac{d\omega}{dk} \\
\vec{E} = \vec{E}_{\vec{k}} \exp(i\psi) \\
\begin{cases} 
\omega = -\frac{\partial \psi}{\partial t} \\ 
\vec{k} = \nabla \psi 
\end{cases} 
\Rightarrow \frac{\partial \vec{k}}{\partial t} + \nabla \omega = 0, \omega(\vec{k}) \\
\frac{\partial \vec{k}}{\partial t} + \vec{v}_g \cdot\nabla\vec{k} = 0
\end{gathered}
$$

在以群速度运动的参考系中，$\vec{k}$ 为常数，类似于随体导数。说明波包是以群速度在空间中传播。

$$\vec{v}_g = \frac{\partial \omega}{\partial \vec{k}}$$

根据相速度于群速度的定义可得瑞利群速度公式：

$$v_g = \frac{d\omega}{dk} = v_p + k \frac{dv_p}{dk} = v_p - \lambda \frac{dv_p}{d\lambda}$$

$$
\begin{cases} 
\frac{dv_p}{dk} = 0 & \text{, 无色散} \\ 
\frac{dv_p}{dk} < 0 & \text{, 正色散} \\ 
\frac{dv_p}{dk} > 0 & \text{, 反色散} 
\end{cases}
$$

### 偏振

$$
\begin{gathered}
\vec{E} = (E_y \vec{e}_y + E_z \vec{e}_z) \exp(ikx - i\omega t) \\
E_y = E_{y0} e^{i\alpha}, \quad E_z = E_{z0} e^{i\beta}
\end{gathered}
$$

取 $\delta = \beta - \alpha$

$$\vec{E} = (E_{y0} \vec{e}_y + E_{z0} e^{i\delta} \vec{e}_z) \exp[i(kx - \omega t + \alpha)]$$

圆偏振 $\delta = \pm \frac{\pi}{2}$

$$\left(\frac{E_y}{E_{y0}}\right)^2 + \left(\frac{E_z}{E_{z0}}\right)^2 = 1$$

$\frac{E_z}{E_y} = -i$（左旋），$\frac{E_z}{E_y} = i$（右旋）（沿着波方向）

线偏振 $\delta = 2n\pi$

# 线性波分析方法

方程的线性化：非线性 $\rightarrow$ 小扰动 $\rightarrow$ 线性化

平衡位置对小扰动的响应特性

$$f = f_0 + f_1 \text{（平衡量 + 扰动量）}, \quad \left|\frac{f_1}{f_0}\right| \ll 1$$
## 1. 根据研究对象选取合适的方程
$$
\begin{cases} 
\rho \frac{\partial \vec{u}}{\partial t} + \rho \vec{u} \cdot \nabla \vec{u} = -\nabla p \\ 
\frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \vec{u}) = 0  \\ 
\frac{d}{dt} (p \rho^{-\gamma}) = 0
\end{cases}
$$
动量方程中的 $\vec{u} \cdot \nabla \vec{u}$ 很明显是一个非线性项，非线性方程不满足叠加原理，自然也无法使用傅里叶分解去研究波的各种性质，需要线性化方程。

## 2. 线性化方程

将物理量分解为平衡量加扰动小量

$$\vec{u} = \vec{u}_0 + \vec{u}_1, \quad \rho = \rho_0 + \rho_1, \quad p = p_0 + p_1$$

首先得满足平衡态方程 ($\vec{u}_0, \rho_0, p_0$)

线性化方程

$$
\begin{gathered}
\rho_0 \frac{\partial \vec{u}_1}{\partial t} + \rho_1 \vec{u}_0 \cdot \nabla \vec{u}_0 + \rho_0 \vec{u}_1 \cdot \nabla \vec{u}_0 + \rho_0 \vec{u}_0 \cdot \nabla \vec{u}_1 = -\nabla p_1
\end{gathered}
$$
$$
\frac{\partial \rho_1}{\partial t} + \nabla \cdot (\rho_0 \vec{u}_1) + \nabla \cdot (\rho_1 \vec{u}_0) = 0, \quad \text{假设 } \vec{u}_0 = 0
$$
$$
\begin{gathered}
(p_0 + p_1) (\rho_0 + \rho_1)^{-\gamma} \approx (p_0 + p_1) \rho_0^{-\gamma} \left(1 - \gamma \frac{\rho_1}{\rho_0}\right) \\
= p_0 \rho_0^{-\gamma} \left(1 + \frac{p_1}{p_0}\right) \left(1 - \gamma \frac{\rho_1}{\rho_0}\right) \\
= p_0 \rho_0^{-\gamma} \left(1 + \frac{p_1}{p_0} - \gamma \frac{\rho_1}{\rho_0}\right) = p_0 \rho_0^{-\gamma} \\
\Rightarrow \frac{p_1}{p_0} = \gamma \frac{\rho_1}{\rho_0}
\end{gathered}
$$

现在各个方程都变为线性方程，可以用傅里叶变换将微分方程组变为代数方程组进行求解。
## 3. 根据线性化方程求本征模式

$$
\begin{cases}
\rho_0 \frac{\partial \vec{u}_1}{\partial t} = -\nabla p_1 \\
\frac{\partial \rho_1}{\partial t} + \nabla \cdot (\rho_0 \vec{u}_1) = 0 \\
\frac{p_1}{p_0} = \gamma \frac{\rho_1}{\rho_0}
\end{cases}
$$

作傅里叶变换，扰动量表示为平面波形式

$$
\begin{gathered}
\sum_{\vec{k}, \omega} f_{\vec{k}, \omega} \exp[i(\vec{k} \cdot \vec{r} - \omega t)] \\
\frac{\partial}{\partial t} \rightarrow -i\omega, \quad \nabla \rightarrow i\vec{k}
\end{gathered}
$$
$$
\begin{cases}
-i\omega \rho_0 \vec{u}_1 = -i\vec{k} p_1 \\
-i\omega \rho_1 + \rho_0 i\vec{k} \cdot \vec{u}_1 = 0 \\
p_1 / p_0 = \gamma \rho_1 / \rho_0
\end{cases}
$$

消元求色散关系

$$
\begin{gathered}
-i\omega \rho_0 \vec{k} \cdot \vec{u}_1 = -ik^2 p_1 \\
-i\omega \rho_0 \omega \frac{\rho_1}{\rho_0} = -ik^2 \gamma \frac{\rho_1}{\rho_0} p_0 \\
\omega^2 \rho_0 = k^2 \gamma p_0\\
\frac{\omega}{k} = \sqrt{\frac{\gamma p_0}{\rho_0}} = c_{s}
\end{gathered}
$$

波动模式为声波，由压强驱动。
## 4. 分析本征模特性

(1) 本征模式数量：系数矩阵行列式为 0 解的数量

(2) 纵模与横模，$\vec{u} \parallel \vec{k}$，声波为纵波；不平行又不垂直：混杂波

(3) 波动模式的色散关系，$k$ 与 $\omega$ 的关系

(4) 各扰动量的关系

# 冷等离子体中的线性波

磁化等离子体，$\beta = \frac{p}{B^2/2\mu_0} \ll 1$，忽略压强项

等离子体视为有自由电荷、自由电流的导电介质，将自由电流视为电介质中的位移电流，用 Maxwell 方程描述
$$
\begin{cases} 
\nabla \times \vec{E} = -\frac{\partial \vec{B}}{\partial t} \\ 
\nabla \times \vec{B} = \mu_0 \vec{J} + \mu_0 \varepsilon_0 \frac{\partial \vec{E}}{\partial t} = \mu_0 \varepsilon_0 \overleftrightarrow{\varepsilon} \cdot \frac{\partial \vec{E}}{\partial t} 
\end{cases}
$$
$$
\begin{gathered}
\overleftrightarrow{\varepsilon} = \overleftrightarrow{I} + i \frac{\overleftrightarrow{\sigma}}{\varepsilon_0 \omega} \\
\nabla \times \nabla \times \vec{E} = -\mu_0 \varepsilon_0 \overleftrightarrow{\varepsilon} \cdot \frac{\partial^2 \vec{E}}{\partial t^2} \\
\vec{k} \times (\vec{k} \times \vec{E}) = -\frac{\omega^2}{c^2} \overleftrightarrow{\varepsilon} \cdot \vec{E} \\
\left(\vec{k}\vec{k} - k^2 \overleftrightarrow{I} + \frac{\omega^2}{c^2} \overleftrightarrow{\varepsilon}\right) \cdot \vec{E} = 0
\end{gathered}
$$

点乘 $\vec{k}$

$$\Rightarrow \vec{k} \cdot \overleftrightarrow{\varepsilon} \cdot \vec{E} = 0$$

若为静电扰动 $\vec{B}_1 = 0$
$$
\begin{gathered}
\vec{k} \times \vec{E}_1 = 0, \quad \vec{k} \parallel \vec{E} \text{（静电波为纵波）} \\
\vec{E}_1 = -\nabla \phi_1 = -i\vec{k} \phi_1 \\
\vec{k} \cdot \overleftrightarrow{\varepsilon} \cdot \vec{k} \phi_1 = 0 \Rightarrow \text{色散关系 } \vec{k} \cdot \overleftrightarrow{\varepsilon} \cdot \vec{k} = 0
\end{gathered}
$$

对于一般电磁扰动，求解行列式方程
$$\det \left| \vec{k}\vec{k} - k^2 \overleftrightarrow{I} + \frac{\omega^2}{c^2} \overleftrightarrow{\varepsilon} \right| = 0$$

只要知道了等离子体的介电张量 $\overleftrightarrow{\varepsilon}$ 便可以根据上面方程求得色散关系。

定义无量纲波矢量（大小意义为折射率）
$$
\begin{gathered}
\vec{n} = \frac{c}{\omega} \vec{k} \\
\det \left| \vec{n} \vec{n} - n^2 \overleftrightarrow{I} + \overleftrightarrow{\varepsilon} \right| = 0
\end{gathered}
$$

下面根据双流体方程求解介电张量
$$
\begin{gathered}
m_\alpha n_\alpha \frac{d \vec{u}_\alpha}{dt} = n_\alpha q_\alpha (\vec{E} + \vec{u}_\alpha \times \vec{B}) \\
\Downarrow \text{ 线性化，去掉扰动量下标1} \\
m_\alpha \frac{\partial \vec{u}_\alpha}{\partial t} = q_\alpha (\vec{E} + \vec{u}_\alpha \times \vec{B}_0) \\
-i \omega m_\alpha \vec{u}_\alpha = q_\alpha (\vec{E} + \vec{u}_\alpha \times \vec{B}_0)
\end{gathered}
$$

求介电就要求电导率张量，也就是扰动电流密度与电场的关系
$$\vec{J} = \sum_\alpha n_\alpha q_\alpha \vec{u}_\alpha$$

取 $\vec{B} = B_0 \vec{e}_z$ ，直角坐标
$$
\begin{cases} 
u_{\alpha x} = \frac{i q_\alpha}{m_\alpha \omega} (E_x + u_{\alpha y} B_0) \\ 
u_{\alpha y} = \frac{i q_\alpha}{m_\alpha \omega} (E_y - u_{\alpha x} B_0) \\ 
u_{\alpha z} = \frac{i q_\alpha}{m_\alpha \omega} (E_z)
\end{cases}
$$

$$
\begin{gathered}
\overleftrightarrow{A}_\alpha = \begin{pmatrix} 1 & -i \frac{\omega_{c\alpha}}{\omega} & 0 \\ i \frac{\omega_{c\alpha}}{\omega} & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \\
\beta_\alpha = \frac{q_\alpha}{m_\alpha \omega}, \quad \omega_{c\alpha} = \frac{q_\alpha B_0}{m_\alpha}
\end{gathered}
$$

动量方程化为：
$$
\begin{gathered}
\overleftrightarrow{A}_\alpha \cdot \vec{u}_\alpha = i \beta_\alpha \vec{E} \\
\vec{u}_\alpha = \overleftrightarrow{A}_\alpha^{-1} \cdot i \beta_\alpha \vec{E}
\end{gathered}
$$

可以得到电流和电场的关系
$$
\begin{gathered}
\vec{J} = \overleftrightarrow{\sigma} \vec{E} \\
\vec{J} = \sum_\alpha n_\alpha q_\alpha \overleftrightarrow{A}_\alpha^{-1} \cdot i \beta_\alpha \vec{E} \\
\overleftrightarrow{\sigma} = \sum_\alpha n_\alpha q_\alpha i \beta_\alpha \overleftrightarrow{A}_\alpha^{-1} \\
\overleftrightarrow{\varepsilon} = \overleftrightarrow{I} - \frac{1}{\varepsilon_0 \omega^2} \sum_\alpha \frac{n_\alpha q_\alpha^2}{m_\alpha} \overleftrightarrow{A}_\alpha^{-1} = \overleftrightarrow{I} - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega^2} \overleftrightarrow{A}_\alpha^{-1}
\end{gathered}
$$

$$\overleftrightarrow{A}_\alpha^{-1} = \frac{1}{1 - \omega_{c\alpha}^2/\omega^2} \begin{pmatrix} 1 & i \frac{\omega_{c\alpha}}{\omega} & 0 \\ -i \frac{\omega_{c\alpha}}{\omega} & 1 & 0 \\ 0 & 0 & 1 - \frac{\omega_{c\alpha}^2}{\omega^2} \end{pmatrix}$$

$$\overleftrightarrow{\varepsilon} = \begin{pmatrix} S & -iD & 0 \\ iD & S & 0 \\ 0 & 0 & P \end{pmatrix}$$

$$
\begin{gathered}
S = 1 - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega^2 - \omega_{c\alpha}^2} \\
D = \sum_\alpha \frac{\omega_{c\alpha} \omega_{p\alpha}^2}{\omega (\omega^2 - \omega_{c\alpha}^2)} \\
P = 1 - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega^2}
\end{gathered}
$$

各向异性，垂直平行磁场方向不同
① $\vec{B}_0 \rightarrow 0, \omega_{c\alpha} \rightarrow 0$

$$
\begin{gathered}
D \rightarrow 0, \quad S \rightarrow P \rightarrow 1 - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega^2} \\
\overleftrightarrow{\varepsilon} = S \overleftrightarrow{I} \quad \text{（没有磁场退化为各向同性）}
\end{gathered}
$$

② 真空极限 $n_{\alpha 0} \rightarrow 0$ 或 $\omega \rightarrow \infty$

$$
\begin{gathered}
\omega_{p\alpha} = \sqrt{\frac{n_\alpha q_\alpha^2}{\varepsilon_0 m_\alpha}} \rightarrow 0 \\
S \rightarrow 1, \quad P \rightarrow 1, \quad D \rightarrow 0 \\
\overleftrightarrow{\varepsilon} = \overleftrightarrow{I}
\end{gathered}
$$

③ 低频极限 $\omega \ll \omega_{c\alpha}, \omega \ll \omega_{p\alpha}$

$$
\begin{gathered}
S \rightarrow  1 + \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega_{c\alpha}^2} = 1 + \sum_\alpha \frac{n_{\alpha 0} m_\alpha}{\varepsilon_0 B_0^2} = 1 + \frac{\rho_{0}}{\varepsilon_0 B_0^2} = 1 + \frac{c^2}{v_A^2} \\
v_A = \frac{B_0}{\sqrt{\mu_0 \rho_0}} \\
D \rightarrow - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega \omega_{c\alpha}} = - \frac{1}{\omega} \sum_\alpha \frac{n_\alpha q_\alpha}{\varepsilon_0 B_0} = 0 \quad \text{（准中性）} \\
P \rightarrow \infty
\end{gathered}
$$

$\vec{k}$ 与 $\vec{B}_0$ 构成的平面 ($x-z$) 夹角 $\theta$

$$
\begin{gathered}
\vec{k} = k \sin \theta \vec{e}_x + k \cos \theta \vec{e}_z \\
\vec{n} = n \sin \theta \vec{e}_x + n \cos \theta \vec{e}_z
\end{gathered}
$$

$$
\begin{vmatrix}
S - n^2 \cos^2 \theta & -iD & n^2 \sin \theta \cos \theta \\
iD & S - n^2 & 0 \\
n^2 \sin \theta \cos \theta & 0 & P - n^2 \sin^2 \theta
\end{vmatrix}
= 0
$$

$$A n^4 - B n^2 + C = 0$$

$$
\begin{cases} 
A = P \cos^2 \theta + S \sin^2 \theta \\ 
B = SP (1 + \cos^2 \theta) + (S^2 - D^2) \sin^2 \theta = SP (1 + \cos^2 \theta) + RL \sin^2 \theta \\ 
C = P (S^2 - D^2) = PRL 
\end{cases}
$$

$$
\begin{gathered}
R = S + D = 1 - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega (\omega + \omega_{c\alpha})}, \quad S = \frac{R + L}{2} \\
L = S - D = 1 - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega (\omega - \omega_{c\alpha})}, \quad D = \frac{R - L}{2}
\end{gathered}
$$

改写为 Alice 形式

$$\tan^2 \theta = - \frac{P (n^2 - R) (n^2 - L)}{(n^2 - P) (S n^2 - RL)}$$

色散关系

$$n^2 = \frac{1}{2A} \left(B \pm \sqrt{B^2 - 4AC}\right)$$

存在两种不同波动模式

当 $n^2 > 0$，$k$ 为实数，波可以传播

当 $n^2 < 0$，$k$ 为虚数，为衰减波

当 $n^2 = 0$，称为截止，$\frac{\omega}{k} \rightarrow \infty$，波将被反射

当 $n^2 \rightarrow \infty$，称为共振，$\frac{\omega}{k} \rightarrow 0$，$v_g \rightarrow 0$，波能汇聚

注：空间全空间的 Fourier 变换，假设空间均匀，

实际上，空间参数弱不均匀

$$|\Delta k / k^2| \ll 1, \quad |\lambda / L| \ll 1$$

一个波长尺度下，波矢变化很小，可用 WKB 近似

等离子体参数变化（如密度）引起 $n$ 变化

如在从 $\rho$ 小 $\rightarrow \rho$ 大，出现截止、共振现象

考虑截止，$C = 0$ 的波支有一支截止

① $P = 0$，寻常波（中端波）截止频率：

$$\omega_p = \sqrt{\omega_{pe}^2 + \omega_{pi}^2} \sim \omega_{pe}$$

② $R = 0$，右旋波截止频率：

$$\omega_R \sim \left(\omega_{pe}^2 + \omega_{ce}^2/4\right)^{\frac{1}{2}} + \omega_{ce}/2$$

③ $L = 0$，左旋波截止频率：

$$\omega_L \sim \left(\omega_{pe}^2 + \omega_{ce}^2/4\right)^{\frac{1}{2}} - \omega_{ce}/2$$

考虑共振，$A = 0$，有一支波共振

$$
\begin{gathered}
A = P \cos^2 \theta + S \sin^2 \theta \\
\tan^2 \theta = - \frac{P}{S}
\end{gathered}
$$

共振频率与传播方向有关

偏振，将 $n(\omega)$ 代入

$$\left(\vec{n} \vec{n} - n^2 \overleftrightarrow{I} + \overleftrightarrow{\varepsilon}\right) \cdot \vec{E} = 0$$

得到各分量的相对比值 $\Rightarrow$ 确定场中的方向 $\Rightarrow$ 确定偏振方向

若电场扰动具有静电特征，$\vec{E} = -\nabla \phi$ 形式，静电波模

$\vec{k} \parallel \vec{E}$，纵波，由 $\vec{k} \cdot \overleftrightarrow{\varepsilon} \cdot \vec{k} = 0$，有

$$\tan^2 \theta = -P/S$$

① $\theta = 0, P = 0, v_g = \frac{\partial \omega}{\partial k} = 0$，波不能任意传播

② $\theta = \pi/2, S = 0, v_g = \frac{\partial \omega}{\partial k} = 0$，波不能任意传播

# 低频近似 —— Alfvén 波

$\omega \ll \omega_{ci}$，表现为 MHD 响应特性，双流体 $\rightarrow$ MHD

类比流体力学中的声速

$$\sqrt{\frac{\gamma p}{\rho}} \sim \sqrt{\frac{\gamma_m B^2/2\mu_0}{\rho}} \propto \frac{B}{\sqrt{\mu_0 \rho}} = v_A \text{（Alfvén 速度）}$$

$$
\begin{gathered}
S \sim L \sim R \sim 1 + \frac{c^2}{v_A^2} \\
D \sim 0, \quad P \sim \infty \\
\tan^2 \theta = \frac{(n^2 - S)^2}{S (n^2 - S)}
\end{gathered}
$$

$$
\begin{cases} 
n^2 - S = 0 & \text{（由磁压引起，压缩 Alfvén 波）} \\ 
n^2 = S (1 + \tan^2 \theta) = S / \cos^2 \theta & \text{（磁力线发生切变，剪切 Alfvén 波）} 
\end{cases}
$$

Alfvén波 的扰动图像

$$\vec{k} \cdot \overleftrightarrow{\varepsilon} \cdot \vec{E} = 0$$

$$
\begin{pmatrix}
S - n^2 \cos^2 \theta & 0 & n^2 \sin \theta \cos \theta \\
0 & S - n^2 & 0 \\
n^2 \sin \theta \cos \theta & 0 & P - n^2 \sin^2 \theta
\end{pmatrix}
\begin{pmatrix}
E_x \\
E_y \\
E_z
\end{pmatrix}
= 0
$$

$P \rightarrow \infty, E_z = 0, \vec{E} \perp \vec{B}_0$

由 $\vec{u}_\alpha$ 与 $\vec{E}$ 关系，$u_{\alpha z} = 0, \vec{u}_\alpha \perp \vec{B}_0$ ($v_A \ll c$)

## ① 剪切 Alfvén 波

$$
\begin{gathered}
n^2 = \left(1 + \frac{c^2}{v_A^2}\right) \frac{1}{\cos^2 \theta} \sim \frac{c^2}{v_A^2 \cos^2 \theta} \\
\frac{\omega^2}{k^2} = v_A^2 \cos^2 \theta \\
\omega = k v_A \cos \theta = k_z v_A \\
\vec{v}_g = \nabla_{\vec{k}} \omega = v_A \vec{e}_z \quad \text{（沿着磁力线传播）}
\end{gathered}
$$

$$
\begin{gathered}
E_y = 0, \quad E_x \neq 0 \\
\vec{E} + \vec{u}_\alpha \times \vec{B}_0 = 0 \\
\vec{u}_{\alpha \perp} = \frac{\vec{E} \times \vec{B}_0}{B_0^2}
\end{gathered}
$$

$\vec{u}_\alpha$ 沿 $y$ 方向

$$
\begin{gathered}
\frac{\partial \vec{B}}{\partial t} = -\nabla \times \vec{E} \\
-i \omega \vec{B} = -i \vec{k} \times \vec{E} \\
\omega \vec{B} = \vec{k} \times \vec{E} = k \cos \theta E_x \vec{e}_y \Rightarrow \vec{B} \perp \vec{B}_0 \\
\vec{k} \cdot \vec{u}_{\alpha \perp} = 0 \Rightarrow \nabla \cdot \vec{u}_{\alpha \perp} = 0 \quad \text{（流体不可压缩（横向））}
\end{gathered}
$$

磁张力提供恢复力

## ② 压缩 Alfvén 波
$$
\begin{gathered}
n^2 = 1 + \frac{c^2}{v_A^2} \sim \frac{c^2}{v_A^2} \\
\omega = k v_A \\
\vec{v}_g = v_A \vec{e}_k \quad \text{（沿波的方向传播）}
\end{gathered}
$$

$$
\begin{gathered}
E_y \neq 0, \quad E_x = 0 \\
\vec{u}_\alpha = \frac{\vec{E} \times \vec{B}_0}{B_0^2} = u_{\alpha x} \vec{e}_x \\
\vec{B} = \frac{k}{\omega} \vec{k} \times \vec{E} = \frac{k}{\omega} E_y (\sin \theta \vec{e}_z - \cos \theta \vec{e}_x)
\end{gathered}
$$

$\nabla \cdot \vec{u}_\alpha \neq 0$，可压缩，磁压力为恢复力

# 磁流体力学波

上面在低频近似下计算出介电张量导出阿尔芬波是没有任何问题的，双流体框架自然包含磁流体中所存在的波动模式。

在低频近似下双流体方程可以退化为MHD方程，只用MHD同样可以导出阿尔芬波，而不必进行上面繁琐的介电张量求解。

$$
\begin{cases}
\dfrac{\partial \rho}{\partial t}+\nabla\cdot(\rho\vec{u})=0\\[6pt]
\rho\dfrac{d\vec{u}}{dt}=-\nabla p+\vec{J}\times\vec{B}\\[6pt]
\nabla\times\vec{B}=\mu_0\vec{J}\\[6pt]
\nabla\times\vec{E}=-\dfrac{\partial \vec{B}}{\partial t}\\[6pt]
\vec{E}+\vec{u}\times\vec{B}=0 \\[6pt]
p\rho^{-\gamma}=c \\
\end{cases}
$$

稍微合并一下

$$
\begin{cases}
\dfrac{\partial \rho}{\partial t}+\nabla\cdot(\rho\vec{u})=0\\ \\
\rho\dfrac{d\vec{u}}{dt}=-\nabla p+\frac{1}{\mu_0}(\nabla\times\vec{B})\times\vec{B}\\ \\
\frac{\partial \vec{B}}{\partial t}=\nabla\times(\vec{u}\times\vec{B})\\ \\
p\rho^{-\gamma}=c \\
\end{cases}
$$

线性化

$$
\begin{cases}
\dfrac{\partial \rho_1}{\partial t}+\rho_0\nabla\cdot\vec{u}_1=0\\[8pt]
\rho_0\dfrac{\partial\vec{u}_1}{\partial t}=-\nabla p_1+\dfrac{1}{\mu_0}(\nabla\times\vec{B}_1)\times\vec{B}_0\\[10pt]
\dfrac{\partial\vec{B}_1}{\partial t}=\nabla\times(\vec{u}_1\times\vec{B}_0)\\[10pt]
\dfrac{p_1}{p_0}=\gamma\dfrac{\rho_1}{\rho_0}
\end{cases}
\Rightarrow
\begin{cases}
\dfrac{\partial p_1}{\partial t}+\gamma p_0\nabla\cdot\vec{u}_1=0\\[10pt]
\rho_0\dfrac{\partial\vec{u}_1}{\partial t}=-\nabla p_1+\dfrac{1}{\mu_0}(\nabla\times\vec{B}_1)\times\vec{B}_0\\[10pt]
\dfrac{\partial\vec{B}_1}{\partial t}=\nabla\times(\vec{u}_1\times\vec{B}_0)
\end{cases}
$$

做傅里叶变换

$$
\left\{
\begin{aligned}
\omega p_1&=\gamma p_0\,\vec{k}\cdot\vec{u}_1\\[6pt]
-\omega\rho_0\vec{u}_1&=-p_1\vec{k}+\frac{1}{\mu_0}(\vec{k}\times\vec{B}_1)\times\vec{B}_0\\[6pt]
\omega\vec{B}_1&=-\vec{k}\times(\vec{u}_1\times\vec{B}_0)
\end{aligned}
\right.
$$

全合并到动量方程

$$
\Rightarrow\ 
\omega\rho_0\vec{u}_1=
\frac{\gamma p_0(\vec{k}\cdot\vec{u}_1)\vec{k}}{\omega}
+\frac{1}{\mu_0\omega}\left[\vec{k}\times\left[\vec{k}\times(\vec{u}_1\times\vec{B}_0)\right]\right]\times\vec{B}_0
$$

$$
\omega^2\vec{u}_1=c_s^2(\vec{k}\cdot\vec{u}_1)\vec{k}
+v_A^2\left\{\vec{k}\times\left[\vec{k}\times(\vec{u}_1\times\vec{b}_0)\right]\right\}\times\vec{b}_0
$$

得到了只含有$\vec{u}_1$ 的方程，剩下只需要在直角坐标下慢慢展开

可以不失一般性的在xz平面上，设 $\vec{b}_0=\vec{e}_z,\ \vec{k}=k_{\parallel}\vec{e}_z+k_{\perp}\vec{e}_x$，带入展开可以得到

$$
\omega^2
\begin{pmatrix}
u_{1x}\\
u_{1y}\\
u_{1z}
\end{pmatrix}
=
c_s^2(u_{1x}k_{\perp}+u_{1y}k_{\parallel})
\begin{pmatrix}
k_{\perp}\\
0\\
k_{\parallel}
\end{pmatrix}
+
v_A^2
\begin{pmatrix}
u_{1x}(k_{\parallel}^2+k_{\perp}^2)\\
k_{\parallel}^2u_{1y}\\
0
\end{pmatrix}
$$

① 首先看 $\vec{e}_y$ 方向，可以看到这个方向不受到热压的影响

$$
\omega^2u_{1y}=v_A^2k_{\parallel}^2u_{1y}
\Rightarrow\ 
\omega^2=k_{\parallel}^2v_A^2
$$

即剪切阿尔芬波

② 其余方向，

$$
\begin{pmatrix}
\omega^2-c_s^2k_{\perp}^2-v_A^2k^2 & -c_s^2k_{\parallel}k_{\perp}\\[6pt]
-c_s^2k_{\perp}k_{\parallel} & \omega^2-c_s^2k_{\parallel}^2
\end{pmatrix}
\begin{pmatrix}
u_{1x}\\
u_{1z}
\end{pmatrix}
=0
$$

系数矩阵行列式为0

$$
\det=\omega^4-(c_s^2k^2+v_A^2k^2)\omega^2+c_s^2v_A^2k_{\parallel}^2k_{\perp}^2=0
$$

$$
\frac{\omega^2}{k^2}
=\frac{c_s^2+v_A^2}{2}\left(
1\pm\sqrt{
1-\frac{4c_s^2v_A^2\cos^2\theta}{(c_s^2+v_A^2)^2}
}
\right)
$$

即磁声波

# 存在平衡流时的磁流体波

考虑 $\vec{u}_0$ 为均匀流

$$
\begin{cases}
\frac{\partial}{\partial t} \rho + \nabla \cdot (\rho \vec{u}) = 0 \\
\rho \frac{d\vec{u}}{dt} = -\nabla p+\vec{J} \times \vec{B} \\
\nabla \times (\vec{u} \times \vec{B}) = \frac{\partial \vec{B}}{\partial t} \\
\nabla \times \vec{B} = \mu_0 \vec{J} \\
\frac{d}{dt} (p \rho^{-\gamma}) = 0
\end{cases}
$$

$$
\Rightarrow
\begin{cases}
\rho_0 \frac{\partial \vec{u}_1}{\partial t} + \rho_0 \vec{u}_0 \cdot \nabla \vec{u}_1 = -\nabla p_1 + \frac{1}{\mu_0} (\nabla \times \vec{B}_1) \times \vec{B}_0 & \text{①} \\
\nabla \times (\vec{u}_1 \times \vec{B}_0 + \vec{u}_0 \times \vec{B}_1) = \frac{\partial \vec{B}_1}{\partial t} & \text{②} \\
\left( \frac{\partial}{\partial t} +\vec{u_{0}}\cdot \nabla \right)p_{1}+\gamma p_{0}\nabla\cdot \vec{u_{1}}=0 & \text{③ }
\end{cases}
$$

③ 的推导如下，首先将状态方程展开，

$$
\left( \frac{\partial}{\partial t} +\vec{u}\cdot \nabla \right)p-\frac{\gamma p}{\rho}\left( \frac{\partial}{\partial t} +\vec{u}\cdot \nabla \right)\rho=0
$$

再代入连续性方程得，

$$
\left( \frac{\partial}{\partial t} +\vec{u}\cdot \nabla \right)p+\gamma p\nabla\cdot \vec{u}=0
$$

线性化后，

$$
\left( \frac{\partial}{\partial t} +\vec{u_{0}}\cdot \nabla \right)p_{1}+\gamma p_{0}\nabla\cdot \vec{u_{1}}=0
$$

用到了一开始的均匀流条件 $\nabla\cdot \vec{u}=0$ ，将多出来的平衡流项与时间偏导并为类似随体导数，作变换

$$\left(\frac{\partial}{\partial t} + \vec{u}_0 \cdot \nabla\right) \rightarrow (-i\omega + i\vec{u}_0 \cdot \vec{k}) \rightarrow -i(\omega - \vec{k} \cdot \vec{u}_0)$$

定义 $\bar{\omega} = \omega - \vec{k} \cdot \vec{u}_0$，则 $\left(\frac{\partial}{\partial t} + \vec{u}_0 \cdot \nabla\right) \rightarrow -i\bar{\omega}$

作代换后，可直接看出来 ①  ③与没有 $\vec{u}_0$ 的形式完全一致

将 ②式化简一下，

$$
\begin{gathered}
\nabla \times (\vec{u}_1 \times \vec{B}_0) + \nabla \times (\vec{u}_0 \times \vec{B}_1) = \frac{\partial \vec{B}_1}{\partial t} \\
\nabla \times (\vec{u}_0 \times \vec{B}_1) = \vec{u}_0 (\nabla \cdot \vec{B}_1) - \vec{B}_1 (\nabla \cdot \vec{u}_0) + (\vec{B}_1 \cdot \nabla) \vec{u}_0 - (\vec{u}_0 \cdot \nabla) \vec{B}_1= -(\vec{u}_0 \cdot \nabla) \vec{B}_1
\end{gathered}
$$

③ 式最终可以化简为

$$\left(\frac{\partial}{\partial t} + \vec{u}_0 \cdot \nabla\right) \vec{B}_1 = \nabla \times (\vec{u}_1 \times \vec{B}_0)$$

作代换后也与 $\vec{u}_0 = 0$ 时形式一致

只需将 $\vec{u}_0 = 0$ 的色散关系作代换 $\omega \rightarrow \bar{\omega}$，即可得到存在平衡流时的色散关系

$$(\bar{\omega}^2 - k_\parallel^2 v_A^2) [\bar{\omega}^4 - \bar{\omega}^2 k^2 (v_A^2 + c_s^2) + k^2 k_\parallel^2 v_A^2 c_s^2] = 0$$

同样存在两支波动
## 剪切 Alfvén 波

$$
\begin{gathered}
\bar{\omega}^2 = k_\parallel^2 v_A^2 \\
(\omega - \vec{k} \cdot \vec{u}_0)^2 = k_\parallel^2 v_A^2 \\
\omega = \vec{k} \cdot \vec{u}_0 \pm k_\parallel v_A
\end{gathered}
$$
## 磁声波

$$
\begin{gathered}
\bar{\omega}^2 = \frac{k^2}{2} \left(v_A^2 + c_s^2 \pm \sqrt{(v_A^2 + c_s^2)^2 - 4 v_A^2 c_s^2 \cos^2 \theta}\right) \\
\omega = \vec{k} \cdot \vec{u}_0 \pm \sqrt{\frac{k^2}{2} \left(v_A^2 + c_s^2 \pm \sqrt{(v_A^2 + c_s^2)^2 - 4 v_A^2 c_s^2 \cos^2 \theta}\right)}
\end{gathered}
$$

最终的色散关系都多出了多普勒频移项，相比于不存在平衡流的情况仅相当于做了一个坐标变换。

# 不可压缩近似

由于单独考虑剪切阿尔芬波其具有不可压缩性，直接在磁流体方程中引入不可压缩近似 $\nabla \cdot \vec{u} = 0 \Rightarrow \vec{k} \cdot \vec{u}_1 = 0$

$$
\begin{cases}
\frac{\partial}{\partial t} \rho + \nabla \cdot (\rho \vec{u}) = 0 \\
\rho \frac{d\vec{u}}{dt} = -\nabla p + \vec{J} \times \vec{B} \\
\nabla \times \vec{B} = \mu_0 \vec{J} \\
\nabla \times \vec{E} = -\frac{\partial \vec{B}}{\partial t} \\
\vec{E} + \vec{u} \times \vec{B} = 0 \\
p \rho^{-\gamma} = c
\end{cases}
$$

$$
\Rightarrow
\begin{cases}
\frac{\partial}{\partial t} \rho_1 + \rho_0 \nabla \cdot \vec{u}_1 = 0 \\
\rho_0 \frac{\partial \vec{u}_1}{\partial t} = -\nabla p_1 + \vec{J}_1 \times \vec{B}_0 \\
\nabla \times \vec{B}_1 = \mu_0 \vec{J}_1 \\
\nabla \times \vec{E}_1 = -\frac{\partial \vec{B}_1}{\partial t} \\
\vec{E}_1 + \vec{u}_1 \times \vec{B}_0 = 0 \\
p_1 / p_0 = \gamma \rho_1 / \rho_0
\end{cases}
$$

$$
\Rightarrow
\begin{cases}
-i\omega \rho_1 = 0 \\
-i\omega \rho_0 \vec{u}_1 = -i\vec{k} p_1 + \vec{J}_1 \times \vec{B}_0 \\
i\vec{k} \times \vec{B}_1 = \mu_0 \vec{J}_1 \\
i\vec{k} \times \vec{E}_1 = i\omega \vec{B}_1 \\
\vec{E}_1 + \vec{u}_1 \times \vec{B}_0 = 0 \\
p_1 = \gamma \frac{p_0}{\rho_0} \rho_1
\end{cases}
$$

处理动量方程

$$
\begin{gathered}
-i\omega \rho_0 \vec{u}_1 = -i p_1 \vec{k} + \frac{i\vec{k} \times \vec{B}_1}{\mu_0} \times \vec{B}_0 \\
-\omega \rho_0 \vec{u}_1 = -p_1 \vec{k} + \frac{1}{\mu_0} [- \vec{k} (\vec{B}_0 \cdot \vec{B}_1) + \vec{B}_1 (\vec{B}_0 \cdot \vec{k})] \\
-\omega \rho_0 \vec{u}_1 = -\left[p_1 + \frac{1}{\mu_0} (\vec{B}_0 \cdot \vec{B}_1)\right] \vec{k} + \frac{(\vec{B}_0 \cdot \vec{k})}{\mu_0} \vec{B}_1
\end{gathered}
$$

$\nabla \cdot \vec{u}_1 = 0, \nabla \cdot \vec{B}_1 = 0 \Rightarrow \vec{k} \cdot \vec{u}_1 = \vec{k} \cdot \vec{B}_1 = 0$

因此 $\vec{u}_1 \perp \vec{k}, \vec{B}_1 \perp \vec{k}$

上式可分为两个垂直方向，平行 $\vec{k}$ 方向与垂直$\vec{k}$ 方向

$$
\begin{cases}
\left[p_1 + \frac{1}{\mu_0} (\vec{B}_0 \cdot \vec{B}_1)\right] \vec{k} = 0 & \text{①} \\
-\omega \rho_0 \vec{u}_1 = \frac{(\vec{B}_0 \cdot \vec{k})}{\mu_0} \vec{B}_1 & \text{②}
\end{cases}
$$

$$
\begin{gathered}
\vec{B}_1 = \frac{1}{\omega} (\vec{k} \times \vec{E}_1) = -\frac{1}{\omega} \vec{k} \times (\vec{u}_1 \times \vec{B}_0) \\
= -\frac{1}{\omega} [(\vec{k} \cdot \vec{B}_0) \vec{u}_1 - (\vec{k} \cdot \vec{u}_1) \vec{B}_0] \\
= -\frac{\vec{k} \cdot \vec{B}_0}{\omega} \vec{u}_1 \quad \text{，代入 ②}
\end{gathered}
$$

$$
\begin{gathered}
-\omega \rho_0 \vec{u}_1 = -\frac{(\vec{B}_0 \cdot \vec{k})^2}{\mu_0 \omega} \vec{u}_1 \\
\mu_0 \rho_0 \omega^2 = B_0^2 k^2 \cos^2 \theta \\
\omega^2 = k^2 v_A^2 \cos^2 \theta
\end{gathered}
$$

得到剪切阿尔芬波的色散关系

① 式的物理意义也是清晰的

磁压强定义为 $\frac{B^2}{2\mu_0}$，忽略高阶小量后总的磁压

$$\frac{(\vec{B}_0 + \vec{B}_1)^2}{2\mu_0} \approx \frac{B_0^2}{2\mu_0} + \frac{\vec{B}_0 \cdot \vec{B}_1}{\mu_0}$$

$\nabla \cdot \vec{u}_1 = 0$ 导致 $\rho_1 = 0$，又有 $p_1 = \gamma \frac{p_0}{\rho_0} \rho_1$

从而 $p_1 = 0$，因此 $\vec{B}_0 \cdot \vec{B}_1 / \mu_0 = 0$ （扰动磁压为 0）

因此以热压和磁压作为恢复力的快波与慢波消失

# 平行磁场方向传播的波

$\vec{k} \parallel \vec{B}_0, \theta = 0$，Alice 形式 $\tan \theta = 0$

$$P (n^2 - R) (n^2 - L) = 0$$

$P = 0$ 或 $n^2 = R$ 或 $n^2 = L$ 三种波动

## ① 朗缪尔振荡

$$P = 0 \Rightarrow \omega = \left(\omega_{pi}^2 + \omega_{pe}^2\right)^{\frac{1}{2}} = \omega_p$$

$\omega$ 与 $k$ 无关，没有波能量传播，振荡局限在局域位置

等离子体相当于空间分布的独立振子

$$\omega \vec{B} = \vec{k} \times \vec{E} \Rightarrow \vec{B} = 0, \quad \vec{E} \parallel \vec{k}$$

$\therefore \vec{E} \parallel \vec{k} \parallel \vec{B}_{0}$ 静电振荡，也称为等离子体静电振荡

$$\vec{u}_\alpha = i \beta_\alpha \overleftrightarrow{A}_\alpha^{-1} \cdot \vec{E} = i \beta_\alpha \vec{E} \Rightarrow \vec{u}_\alpha \parallel \vec{E}$$

电子离子方向相反，导致电荷分离产生 $\vec{E}$ （恢复力）

$\vec{u}_{\alpha}$ 与 $\vec{E}$ 有 $\pi/2$ 的相位差，存在动能势能相互交换

## ② 右旋圆偏振波：$n^2 = R$

$$n^2 = 1 - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega (\omega + \omega_{c\alpha})} = 1 - \frac{\omega_{pe}^2}{\omega (\omega - \omega_{ce})} - \frac{\omega_{pi}^2}{\omega (\omega + \omega_{ci})}$$

无 $\vec{B}_0$ 为线偏振波，有 $\vec{B}_0$ 时，为圆偏振波

$$
\begin{pmatrix}
S - n^2 \cos^2 \theta & -iD & n^2 \sin \theta \cos \theta \\
iD & S - n^2 & 0 \\
n^2 \sin \theta \cos \theta & 0 & P - n^2 \sin^2 \theta
\end{pmatrix}
\begin{pmatrix}
E_x \\
E_y \\
E_z
\end{pmatrix}
= 0
$$

$$R = S + D, \quad L = S - D, \quad n^2 = R, \quad \theta = 0$$

$$
\begin{pmatrix}
S - n^2 & -iD & 0 \\
iD & S - n^2 & 0 \\
0 & 0 & P
\end{pmatrix}
\begin{pmatrix}
E_x \\
E_y \\
E_z
\end{pmatrix}
= 0
$$

$$
\begin{gathered}
P \neq 0 \Rightarrow E_z = 0 \Rightarrow \vec{E} \perp \vec{k} \\
\frac{E_x}{E_y} = \frac{iD}{S - n^2} = \frac{iD}{S - R} = \frac{iD}{-D} = -i \quad \text{（圆偏振波（右旋））}
\end{gathered}
$$

$$\omega_R \sim \left(\omega_{pe}^2 + \omega_{ce}^2/4\right)^{\frac{1}{2}} + \omega_{ce}/2 \quad \text{（截止频率）}$$

$\omega_{ce}$ 为共振频率

i) $\omega > \omega_R$，高频波

$$\omega \gg \omega_{ce}, \quad n^2 = 1 - \frac{\omega_{pe}^2}{\omega^2} \Rightarrow \omega^2 = \omega_{pe}^2 + k^2 c^2 \cong k^2 c^2$$

ii) $\omega_{ce} < \omega < \omega_R, n^2 < 0$，波不能传播

iii) $\omega < \omega_{ce}$，电子回旋波，左旋转方向与 $e$ 方向相同

当 $\omega \sim \omega_{ce}$ 时，发生共振 —— 电子回旋共振

电子回旋波段通常称为频率段 ($\omega \gg \omega_{ci}$) 则

$$n^2 \sim 1 - \frac{\omega_{pe}^2}{\omega(\omega - \omega_{ce})}$$

$\omega = \omega_{ce}/2$ 时有极小值

$\omega < \omega_{ce}/2, v_g$ 随 $\omega$ 增加而增加，称为哨声波

当 $\omega_{ci} \ll \omega \ll \omega_{ce}$

$$
\begin{gathered}
n^2 \sim \frac{\omega_{pe}^2}{\omega \omega_{ce}} \\
v_p = \frac{c(\omega \omega_{ce})^{\frac{1}{2}}}{\omega_{pe}} \propto \omega^{\frac{1}{2}}
\end{gathered}
$$

高频传播快

## ④ 左旋圆偏振波 $n^2 = L$

$$
\begin{gathered}
n^2 = 1 - \frac{\omega_{pe}^2}{\omega(\omega + \omega_{ce})} - \frac{\omega_{pi}^2}{\omega(\omega - \omega_{ci})} \\
\vec{E} \perp \vec{k}, \quad \frac{E_x}{E_y} = i \quad \text{（左旋）} \\
\omega_L \sim \left(\omega_{pe}^2 + \omega_{ce}^2/4\right)^{\frac{1}{2}} - \omega_{ce}/2
\end{gathered}
$$

$\omega_{ci} < \omega < \omega_L$，截止

$\omega < \omega_{ci}$，离子回旋波

# 法拉第旋转

任一垂直 $\vec{B_{0}}$ 振荡的线偏振波都可分解为大小一致的左右旋波叠加，由于波速不同，传播一段距离后，合成的线偏振波方向会发生变化，极化方向产生旋转

传播距离 $z$，则旋转角（左旋为正）

$$
\begin{gathered}
\Delta \phi = \frac{1}{2} (k_L - k_R) z \\
n_L - n_R \sim 1 - \frac{\omega_{pe}^2}{2\omega^2} \left(1 - \frac{\omega_{ce}}{\omega}\right) - \left(1 - \frac{\omega_{pe}^2}{2\omega^2} \left(1 + \frac{\omega_{ce}}{\omega}\right)\right) = \frac{\omega_{pe}^2 \omega_{ce}}{\omega^3} \\
\Delta \phi = \frac{1}{2} \cdot \frac{\omega_{pe}^2 \omega_{ce}}{c \omega^3} \cdot \omega = \frac{e^3}{2 \varepsilon_0 c m_e^2 \omega^2} (n_e B_0 z) \\
\Delta \phi = \frac{e^3}{2 \varepsilon_0 c m_e^2 \omega^2} \int_0^z n_e B_0 dz
\end{gathered}
$$

# 垂直磁场方向的波

$\vec{k} \perp \vec{B}_0, \theta = \pi/2$

$$(n^2 - P)(S n^2 - RL) = 0$$

$n^2 = P$ 或 $S n^2 = RL$

## ① 寻常波(普通电磁横波)

$$
\begin{gathered}
n^2 = P, \quad n^2 = 1 - \frac{\omega_p^2}{\omega^2} \quad \text{（与 } B_0 \text{ 无关）} \\
E_x = E_y = 0, \quad E_z \neq 0, \quad \vec{k} \perp \vec{E} \\
u_{\alpha x} = u_{\alpha y} = 0, \quad u_{\alpha z} \neq 0, \quad \vec{u}_\alpha \parallel \vec{B}_0
\end{gathered}
$$

等离子体干涉仪

$$
\begin{gathered}
\Delta \phi = (k_0 - k) z = \frac{\omega}{c} \left[1 - \left(1 - \frac{\omega_p^2}{\omega^2}\right)^{\frac{1}{2}}\right] z \\
= \frac{\omega_{pe}^2 z}{2 c \omega} = \frac{e^2 \lambda}{4 \pi \varepsilon_0 m_e c^2} (n_e z) \\
\Delta \phi = A \int n_e dz
\end{gathered}
$$

## ② 异常波，$n^2 = RL/S$ （X 模）

$$E_z = 0, \quad \frac{E_x}{E_y} = i \frac{S - n^2}{D} = i \frac{D}{S}$$

一般情况下为纵波和横波的混合态

① 低频波 ② 高频波 ③ 高频传播区

共振，$S = 0$

$$1 - \frac{\omega_{pe}^2}{\omega^2 - \omega_{ce}^2} - \frac{\omega_{pi}^2}{\omega^2 - \omega_{ci}^2} = 0$$

两个共振频率，$\omega_{LH}, \omega_{UH}$

$\omega \gg \omega_{ci}, \omega_{pi}$

$$\omega_{UH} = \left(\omega_{ce}^2 + \omega_{pe}^2\right)^{\frac{1}{2}}$$

$\omega \ll \omega_{ce}$

$$
\begin{gathered}
\omega_{LH} = \left(\omega_{ci}^2 + \frac{\omega_{ce}^2 \omega_{pi}^2}{\omega_{ce}^2 + \omega_{pe}^2}\right)^{\frac{1}{2}} \\
\omega_{LH} \approx \begin{cases} \left(\omega_{ci}^2 + \omega_{pi}^2\right)^{\frac{1}{2}} & , \omega_{ce}^2 \gg \omega_{pe}^2 \\ \left(\omega_{ce} \omega_{ci}\right)^{\frac{1}{2}} & , \omega_{ce}^2 \ll \omega_{pe}^2 \end{cases}
\end{gathered}
$$

# 冷等离子体波的热效应

上面讨论的双流体方程都没有考虑热压项，现在加入压强项
$$
\begin{gathered}
n_\alpha m_\alpha \frac{d \vec{u}_\alpha}{dt} = -\nabla p_\alpha + n_\alpha q_\alpha (\vec{E} + \vec{u}_\alpha \times \vec{B}) \\
\frac{\partial}{\partial t} n_\alpha + \nabla \cdot (n_\alpha \vec{u}_\alpha) = 0 \\
p_\alpha \rho_\alpha^{-\gamma} = const
\end{gathered}
$$
$\Downarrow$
$$
\begin{gathered}
n_{\alpha 0} m_\alpha \frac{\partial \vec{u}_\alpha}{\partial t} = -\nabla p_\alpha + n_{\alpha 0} q_\alpha (\vec{E} + \vec{u}_\alpha \times \vec{B}) \\
\frac{\partial}{\partial t} n_\alpha + \nabla \cdot (n_{\alpha 0} \vec{u}_\alpha) = 0 \\
p_\alpha = \frac{\gamma_\alpha p_{\alpha 0}}{n_{\alpha 0}} n_\alpha
\end{gathered}
$$
$\Downarrow$

$$
\begin{gathered}
p_\alpha = \gamma_\alpha p_{\alpha 0} \frac{\vec{k} \cdot \vec{u}_\alpha}{\omega} \\
\vec{u}_\alpha = c_{s\alpha}^2 \frac{\vec{k} \cdot \vec{u}_\alpha}{\omega^2} \vec{k} + i \frac{\omega_{c\alpha}}{\omega} \left(\frac{\vec{E}}{B_0} + \frac{\vec{u}_\alpha \times \vec{B}_0}{B_0}\right) \\
c_{s\alpha} = \left(\frac{\gamma_\alpha p_{\alpha 0}}{n_{\alpha 0} m_\alpha}\right)^{\frac{1}{2}}
\end{gathered}
$$

热压项与方程左边作量级比较，只有 $\frac{c_{s\alpha}^2 k^2}{\omega^2} \sim \frac{c_s^2}{v_p^2} \sim O(1)$ 时，热压作用才明显

同时，热压作用在$\parallel \vec{k}$ 方向，只对纵波分量起作用

$$c_{s\alpha} \sim \left(\frac{\gamma_\alpha n_{\alpha 0} T_\alpha}{n_{\alpha 0} m_\alpha}\right)^{\frac{1}{2}} \sim v_{th\alpha}$$

粒子声速与热速度在一个量级

① 在共振处 $c_{s\alpha} \sim v_p$，热压作用很大

② 有限 Larmor 半径效应（波长与热 Larmor 半径相近）

# 无磁场等离子体波

若 $\vec{B}_0 = 0$，各向同性，$\vec{k} = k \vec{e}_z$

$$
\begin{gathered}
\vec{u}_\alpha = c_{s\alpha}^2 \frac{k^2}{\omega^2} u_{\alpha z} \vec{e}_z + i \frac{q_\alpha}{m_\alpha \omega} \vec{E} \\
\overleftrightarrow{A}_\alpha\cdot \vec{u}_\alpha = i \beta_\alpha \vec{E}
\end{gathered}
$$

$$
\begin{gathered}
\overleftrightarrow{A}_\alpha = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 - \frac{k^2 c_{s\alpha}^2}{\omega^2} \end{pmatrix} \\ \\
\overleftrightarrow{\varepsilon} = \overleftrightarrow{I} - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega^2} \overleftrightarrow{A}_\alpha^{-1} = \begin{pmatrix} 1 - \sum \frac{\omega_{p\alpha}^2}{\omega^2} & 0 & 0 \\ 0 & 1 - \sum \frac{\omega_{p\alpha}^2}{\omega^2} & 0 \\ 0 & 0 & 1 - \sum \frac{\omega_{p\alpha}^2}{\omega^2 - k^2 c_{s\alpha}^2} \end{pmatrix}
\end{gathered}
$$
代入
$$
\begin{gathered}
\vec{n} = n\vec{e_{z}} =\frac{c}{\omega} \vec{k} \\
\det \left| \vec{n} \vec{n} - n^2 \overleftrightarrow{I} + \overleftrightarrow{\varepsilon} \right| = 0
\end{gathered}
$$
$$
\det\begin{pmatrix} -n^{2}+1 - \sum \frac{\omega_{p\alpha}^2}{\omega^2} & 0 & 0 \\ 0 & -n^{2}+1 - \sum \frac{\omega_{p\alpha}^2}{\omega^2} & 0 \\ 0 & 0 & 1 - \sum \frac{\omega_{p\alpha}^2}{\omega^2 - k^2 c_{s\alpha}^2} \end{pmatrix}=0
$$

容易求得两类解

## (i) 电磁横波 $\vec{E} \perp \vec{k}$

$$n^2 = 1 - \sum \frac{\omega_{p\alpha}^2}{\omega^2} = 1 - \frac{\omega_p^2}{\omega^2} \quad \text{（寻常波，热压对其无影响）}$$

## (ii) 纵波解，$\vec{k} \parallel \vec{E}$

$$1 - \sum_\alpha \frac{\omega_{p\alpha}^2}{\omega^2 - k^2 c_{s\alpha}^2} = 0$$

$c_{s\alpha}= 0$，没有热压作用，退化为朗谬尔震荡。
### ① 朗缪尔波，高频波分支

若 $\omega^2 \gg k^2 c_{s\alpha}^2 \Rightarrow v_{p\alpha}^2 \gg v_{th\alpha}^2$ 离子运动忽略

$$\omega^2 = \omega_{pe}^2 + k^2 c_{se}^2 = \omega_{pe}^2 (1 + \gamma_e k^2 \lambda_{De}^2)$$

可视为一维绝热压缩 $\gamma = \frac{2+D}{D} = 3$

$$
\begin{gathered}
v_p = \frac{\omega}{k} = \left(\frac{\omega_{pe}^2}{k^2} + c_{se}^2\right)^{\frac{1}{2}} \\
v_g = \frac{\partial \omega}{\partial k} = \left(\frac{\omega_{pe}^2}{k^2 c_{se}^2} + 1\right)^{-\frac{1}{2}} c_{se}
\end{gathered}
$$

当 $k \lambda_{De} \sim O(1)$，波长与德拜长度相当

$v_g \sim v_p \sim c_{se}$，电子与波共振，发生能量交换（阻尼）

只有 $\lambda_{De} k \ll 1$ 时波才存在

$$\omega \sim \omega_{pe} \left(1 + \frac{3}{2} k^2 \lambda_{De}^2\right)$$

### ② 离子声波，低频分支 $\frac{\omega}{k} \ll c_{se}$，长波模 $k \lambda_{De} \ll 1$

$$
\begin{gathered}
\omega^2 = k^2 \left(c_{si}^2 + \frac{\omega_{pi}^2}{\omega_{pe}^2 + k^2 c_{se}^2} c_{se}^2\right) \\
= k^2 \left(\frac{\gamma_i T_i}{m_i} + \frac{\gamma_e T_e}{m_i} \frac{1}{1 + \gamma_e k^2 \lambda_{De}^2}\right) \\
\frac{\omega}{k} = \left(\frac{\gamma_i T_i + \gamma_e T_e}{m_i}\right)^{\frac{1}{2}} = c_s \quad \text{（离子声速）}
\end{gathered}
$$

声场驱动 电子热运动导致电荷分离

$$\frac{u_e}{u_i} = -\frac{n_i}{n_e} \frac{\omega^2 - k^2 c_{si}^2}{\omega^2 - k^2 c_{se}^2} = \frac{c_{se}^2}{c_{se}^2 - c_s^2} \sim 1 + \frac{c_s^2}{c_{se}^2} \sim 1$$

电子流体与离子流体一致运动，电子略快些

$T_i \lesssim T_e$ 相速度较近，$v_p \sim c_s$，共振，发生朗道阻尼

存在条件 $T_i \ll T_e$

### ③ 离子朗缪尔波 低频分支 $\frac{\omega}{k} \ll c_{se}$，短波近似 $k \lambda_{De} \gg 1$

$$
\begin{gathered}
\omega^2 = \omega_{pi}^2 + k^2 c_{si}^2 = \omega_{pi}^2 (1 + \gamma_i k^2 \lambda_{Di}^2) \\
\frac{u_e}{u_i} = -\frac{m_i}{m_e} \frac{\omega_{pi}^2}{\omega_{pi}^2 + k^2 c_{si}^2 - k^2 c_{se}^2} \sim \frac{1}{\gamma_e k^2 \lambda_{De}^2} \ll 1
\end{gathered}
$$

离子流体速度远大于电子，存在条件 $k^2 \lambda_{Di}^2 \ll 1$ （很难）

# 简化双流体方程推导上述几支波

根据不同波模的频率波长范围，可以通过量级比较忽略掉双流体方程中的一些小量项，

下面是线性化后的双流体方程组
$$
\begin{cases}
\dfrac{\partial}{\partial t}n_{a1}+n_{a0}\nabla\cdot\vec{u}_{a1}=0\\[6pt]
m_a n_{a0}\dfrac{\partial}{\partial t}\vec{u}_{a1}=-\nabla p_{a1}+q_a n_{a0}\vec{E}_1\\[6pt]
\dfrac{p_{a1}}{p_{a0}}=\gamma\dfrac{\rho_{a1}}{\rho_{a0}}\\[6pt]
\nabla\cdot\vec{E}_1=\dfrac{1}{\varepsilon_0}\sum_{\alpha}\left(q_{\alpha}n_{\alpha1}\right)
\end{cases}
$$

## ① 朗缪尔波（高频分支）

$$\omega^2 \gg k^2 C_{sa}^2$$

电子与离子的运动由热压与电场驱动，电场分布来源与电荷分离，由泊松方程描述

$$
\nabla\cdot\vec{E}_1=\dfrac{e}{\varepsilon_0}(n_{i1}-n_{e1}),
$$

比较泊松方程中离子与电子的贡献，同时用到连续性方程与平衡时系统电中性

$$
\dfrac{n_{i1}}{n_{e1}}\sim\dfrac{n_{i0}u_{i1}}{n_{e0}u_{e1}}\sim\dfrac{u_{i1}}{u_{e1}}
$$

速度扰动体现在动量方程中，由动量方程可得

$$
m_{\alpha}n_{\alpha0}\,\omega\,u_{\alpha1}\sim k\,\gamma_{\alpha}\,n_{\alpha1}T_{\alpha}+q_{\alpha}n_{\alpha0}E_1
$$

代入连续性方程 $u_{\alpha1}\sim\frac{kn_{i0}u_{i0}}{\omega}$

$$
m_{\alpha}\omega u_{\alpha1}-\dfrac{k\,\gamma_{\alpha}T_{\alpha}u_{\alpha1}}{\omega}\sim q_{\alpha}E_1
$$
$$
(\omega^2-k^2c_{s\alpha}^2)u_{\alpha1}\sim \omega\dfrac{q_{\alpha}}{m_{\alpha}}E_1
$$
$$
\Rightarrow\quad u_{\alpha1}\sim\dfrac{\omega q_{\alpha}E_1}{m_{\alpha}(\omega^2-k^2c_{s\alpha}^2)}
$$

因为 $\omega^2\gg k^2c_{s\alpha}^2$，近似有

$$
\dfrac{u_{i1}}{u_{e1}}\sim\dfrac{m_e}{m_i}\ll1\Rightarrow\dfrac{n_{i1}}{n_{e1}}\ll1
$$

因此离子对电场的贡献远小于电子，可以忽略，即将离子视为不动背景

剩下下电子的方程：

$$
\begin{cases}
\dfrac{\partial}{\partial t}n_{e1}+n_{e0}\nabla\cdot\vec{u}_{e1}=0\\[6pt]
m_e n_{e0}\dfrac{\partial}{\partial t}\vec{u}_{e1}=-\nabla(\gamma_e n_{e1}T_e)-e n_{e0}\vec{E}_1\\[6pt]
\nabla\cdot\vec{E}_1=-\dfrac{e}{\varepsilon_0}n_{e1}
\end{cases}
$$

考虑纵波传播 $\vec{k}//\vec{E}$，消元得到

$$
\omega m_e n_{e0}\dfrac{\omega n_{e1}}{n_{e0}}=\gamma_e T_e k^2+e n_{e0}\dfrac{e}{\varepsilon_0}n_{e1}
$$

$$
\Rightarrow\ \omega^2=\omega_{pe}^2+\gamma_e c_{se}^2 k^2=\omega_{pe}^{2}(1+\gamma_{e}\lambda_{De}^{2}k^{2})
$$

## ② 离子声波

$$\omega^2\ll k^2 c_{se}^2,\quad k^2\lambda_{De}^2\ll1$$

比较电子动量方程中惯性项与热压项

$$
\dfrac{m_en_{e0}\omega u_{e1}}{k\,\gamma_e n_{e1}T_e}\sim
\dfrac{\omega\,n_{e0}u_{e1}}{c_{se}^2\,k\,n_{e1}}
\sim\dfrac{\omega^2}{k^2c_{se}^2}\ll1
$$

电子惯性项可以忽略，即将电子拟为无质量流体，$m_e=0$

此时由电子动量方程可得

$$
E_1\sim\dfrac{k\,\gamma_e n_{e1}T_e}{e n_{e0}}
$$

代入泊松方程 $\ \nabla\cdot\vec{E}=\dfrac{e}{\varepsilon_0}(n_{i1}-n_{e1})$

$$
\nabla\cdot\vec{E}\sim\dfrac{k^2\gamma_e n_{e1}T_e}{e n_{e0}}
\sim\gamma_e k^2\lambda_{De}^2\dfrac{e}{\varepsilon_0}n_{e1}
$$

$$
\dfrac{\nabla\cdot\vec{E}}{\dfrac{e}{\varepsilon_0}n_{e1}}
\sim \gamma_e k^2\lambda_{De}^2\ll1
\ \Rightarrow\ n_{i1}=n_{e1}
$$
波长远大于德拜球半径，系统保持准中性，方程简化为
$$
\begin{cases}
\dfrac{\partial}{\partial t}n_i+n_{i0}\nabla\cdot\vec{u}_{i1}=0\\[6pt]
m_i n_{i0}\dfrac{\partial}{\partial t}\vec{u}_{i1}=-\nabla(\gamma_i n_{i1}T_i)+e n_{i0}\vec{E}_1\\[6pt]
0=-\nabla(\gamma_e n_{e1}T_e)-e n_{e0}\vec{E}_1
\end{cases}
$$

消元得

$$
\omega^2=\left(\dfrac{\gamma_i T_i+\gamma_i T_e}{m_i}\right)k^2
$$

## ③ 离子朗缪尔波

$$\omega^2\ll k^2 c_{se}^2,\quad k^2\lambda_{De}^2\gg1$$

仍可视为无质量电子 $m_e=0$，此时 $k^2\lambda_{De}^2\gg1$，波长小于德拜球半径，无法满足准中性条件，需保留泊松方程

$$
\begin{cases}
\dfrac{\partial}{\partial t}n_i+n_{i0}\nabla\cdot\vec{u}_{i1}=0\\[6pt]
m_i n_{i0}\dfrac{\partial}{\partial t}\vec{u}_{i1}=-\nabla(\gamma_i n_{i1} T_i)+e n_{i0}\vec{E}_1\\[6pt]
0=-\nabla(\gamma_e n_{e1}T_e)-e n_{e0}\vec{E}_1\\[6pt]
\nabla\cdot\vec{E}_1=\dfrac{e}{\varepsilon_0}(n_{i1}-n_{e1})
\end{cases}
$$

$$
\Rightarrow\ \omega^2=k^2\left[\dfrac{\gamma_i T_i}{m_i}+\dfrac{\gamma_i T_e}{m_i(1+\gamma_i k^2\lambda_{De}^2)}\right]
\approx k^2\left(\dfrac{\gamma_i T_i}{m_i}+\dfrac{\gamma_i T_e}{m_i\gamma_e e^2 k^2\lambda_{De}^2}\right)
=\omega_{pi}^2+k^2c_{si}^2
$$

当 $k^{2}\lambda_{De}^{2}\ll1$ ，满足准中性条件，退化为离子声波。

注意到，

$$
\dfrac{\nabla\cdot\vec{E}}{\dfrac{e}{\varepsilon_0}n_{e1}}
\sim \gamma_e k^2\lambda_{De}^2\gg1
$$

泊松方程可以忽略电子项，也就是可以将电子方程全都扔掉，只考虑离子方程与泊松方程，也可以得到离子声波。
