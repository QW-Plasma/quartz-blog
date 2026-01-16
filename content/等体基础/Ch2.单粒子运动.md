# 均匀场中的漂移

粒子运动方程
$$m \frac{d\vec{v}}{dt} = q \vec{E} + q \vec{v} \times \vec{B}$$

设 $\vec{v} = \vec{v}_c + \vec{v}_E$
$$\begin{cases} m \frac{d\vec{v}_c}{dt} = q \vec{v}_c \times \vec{B} \\ m \frac{d\vec{v}_E}{dt} = q \vec{E} + q \vec{v}_E \times \vec{B} \end{cases}$$

静场 $\frac{d\vec{v}_E}{dt} = 0$
$$\vec{E} + \vec{v}_E \times \vec{B} = 0 \Rightarrow \vec{E} \times \vec{B} + (\vec{v}_E \times \vec{B}) \times \vec{B} = 0 \Rightarrow\vec{E} \times \vec{B} - B^2 \vec{v}_{E\perp} = 0 $$

$$
\Rightarrow \vec{v}_E = \frac{\vec{E} \times \vec{B}}{B^2}(电漂移)
$$

在恒定力 $\vec{F}$ 的作用下，同理可得 $\vec{F} + q \vec{v}_F \times \vec{B} = 0$
$$\vec{v}_F = \frac{\vec{F} \times \vec{B}}{q B^2}$$

与粒子电荷有关，因此能引起电荷分离，例如重力作用 $\vec{F} = m \vec{g}$，引起漂移电流：
$$\vec{j} = \sum n q \vec{v} = n (m_i + m_e) \frac{\vec{g} \times \vec{B}}{B^2} = \frac{\rho \vec{g} \times \vec{B}}{B^2}$$
# 非均匀恒定磁场中的漂移

时空尺度满足以下条件，
$$
\begin{gathered}
|\frac{r_c \nabla B}{B}| \ll 1 \\
|\frac{\partial B}{\partial t} / B \cdot \frac{1}{\omega_c}| \ll 1
\end{gathered}
$$

可以作回旋中心漂移近似
$$\vec{r} = \vec{r}_g + \vec{r}_c, \quad \vec{v} = \vec{v}_g + \vec{v}_c$$

利用摄动理论在导心附近作 Taylor 展开，再在一个回旋周期内平均 $\langle \dots \rangle = \frac{1}{T_c} \int_0^{T_c} (\dots) dt$

$$\langle \vec{r} \rangle = \vec{r}_g \quad \langle \vec{v} \rangle = \vec{v}_g$$

时空尺度分离，$(\vec{b}, \vec{e}_2, \vec{e}_3)$ 构成正交坐标系
$$\vec{b} = \frac{\vec{B}}{B}, \quad \vec{b} \times \vec{e}_2 = \vec{e}_3$$

回旋角 $\omega_c t + \phi$
$$\vec{v}_c = v_\perp (\vec{e}_2 \cos \gamma - \vec{e}_3 \sin \gamma)$$
$$\vec{r}_c = \frac{\vec{b} \times \vec{v}_c}{\Omega_c} = r_c (\vec{e}_2 \sin \gamma + \vec{e}_3 \cos \gamma)$$

$$m (\frac{d\vec{v}_g}{dt} + \frac{d\vec{v}_c}{dt}) = q (\vec{v}_c + \vec{v}_g) \times \vec{B}(\vec{r})$$

$$\vec{B}(\vec{r}) = \vec{B}(\vec{r}_g + \vec{r}_c) \sim \vec{B}(\vec{r}_g) + \vec{r}_c \cdot \nabla \vec{B}(\vec{r}_g)$$

$$m (\frac{d\vec{v}_g}{dt} + \frac{d\vec{v}_c}{dt}) = q (\vec{v}_c + \vec{v}_g) \times (\vec{B}_g + \vec{r}_c \cdot \nabla \vec{B}_g)$$

$$= q [\vec{v}_c \times \vec{B}_g + \vec{v}_g \times \vec{B}_g + \vec{v}_c \times (\vec{r}_c \cdot \nabla \vec{B}_g) + \vec{v}_g \times (\vec{r}_c \cdot \nabla \vec{B}_g)]$$

$\downarrow$ 作回旋平均，$\langle \dots \rangle = \frac{1}{T} \int_0^T \dots dt \quad \langle \vec{r}_c \rangle = 0$

$$m \frac{d\vec{v}_g}{dt} = q \vec{v}_g \times \vec{B}_g + \langle q \vec{v}_c \times (\vec{r}_c \cdot \nabla \vec{B}_g) \rangle$$

$$\nabla \vec{B}_g = \nabla (\vec{b} B_g) = (\nabla B_g) \vec{b} + B_g \nabla \vec{b}$$

$$A = \langle q \vec{v}_c \times [(\vec{r}_c \cdot \nabla B_g) \vec{b} + B_g \vec{r}_c \cdot \nabla \vec{b}] \rangle$$

分别计算右边两项

 $$①= -\langle q \Omega_c \vec{r}_c \vec{r}_c \cdot \nabla B_g \rangle$$

$$= -\langle q \Omega_c r_c^2 (\vec{e}_2 \sin \gamma + \vec{e}_3 \cos \gamma) (\vec{e}_2 \sin \gamma + \vec{e}_3 \cos \gamma) \cdot \nabla B_g \rangle$$

$$= -\frac{1}{2} q \Omega_c r_c^2 (\vec{e}_2 \vec{e}_2 + \vec{e}_3 \vec{e}_3) \cdot \nabla B_g$$

$$= -\frac{1}{2} q \Omega_c r_c^2 (\overleftrightarrow{I} - \vec{b} \vec{b}) \cdot \nabla B_g$$

$$= -\frac{1}{2} q \Omega_c r_c^2 (\nabla B_g - \vec{b} \vec{b} \cdot \nabla B_g)$$

$$= -\frac{1}{2} q \Omega_c r_c^2 \nabla_\perp B_g$$

$$② = \langle q \vec{v}_c \times B_g (\vec{r}_c \cdot \nabla \vec{b}) \rangle$$

$$= \langle q \Omega_c B_g (\vec{r}_c \times \vec{b}) \times (\vec{r}_c \cdot \nabla \vec{b}) \rangle$$

$$= \langle q \Omega_c B_g [(\vec{r}_c \cdot \nabla \vec{b}) \cdot \vec{r}_c \vec{b} - (\vec{r}_c \cdot \nabla \vec{b}) \cdot \vec{b} \vec{r}_c] \rangle$$

再分别计算这两项

$$\langle (\vec{r}_c \cdot \nabla \vec{b}) \cdot \vec{r}_c \rangle = \langle r_c^2 (\vec{e}_2 \sin \gamma + \vec{e}_3 \cos \gamma) \cdot \nabla \vec{b} \cdot (\vec{e}_2 \sin \gamma + \vec{e}_3 \cos \gamma) \rangle \cdot \vec{b}$$

$$= \frac{1}{2} r_c^2 (\vec{e}_2 \cdot \nabla \vec{b} \cdot \vec{e}_2 + \vec{e}_3 \cdot \nabla \vec{b} \cdot \vec{e}_3)$$

$$= \frac{1}{2} r_c^2 \nabla \cdot \vec{b} = \frac{1}{2} r_c^2 \nabla \cdot (\frac{\vec{B}}{B}) = -\frac{1}{2} r_c^2 \frac{1}{B^2} \vec{B} \cdot \nabla B$$

$$\vec{r}_c \cdot \nabla \vec{b} \cdot \vec{b} = \vec{r}_c \cdot \nabla (\vec{b} \cdot \vec{b} / 2) = 0$$

因此
$$m \frac{d\vec{v}_g}{dt} = -\frac{1}{2} q \Omega_c r_c^2 \nabla_\perp B_g - \frac{1}{2} q \Omega_c r_c^2 \vec{b} \cdot \nabla B_g \vec{b}$$

$$= -\mu \nabla_\perp B_g - \mu \vec{b} \cdot \nabla B_g \vec{b} \quad \mu = \frac{m v_\perp^2}{2 B}$$

再分解为平行方向与垂直方向
$$\vec{v}_g = v_\parallel \vec{b} + \vec{v}_d$$

$$m \frac{d}{dt} (v_\parallel \vec{b}) + m \frac{d}{dt} \vec{v}_d = -\mu \nabla_\perp B_g - \mu \vec{b} \cdot \nabla B_g \vec{b} + q \vec{v}_d \times \vec{B}_g$$

$$m \frac{d v_\parallel}{dt} \vec{b} + m v_\parallel \frac{d\vec{b}}{dt} + m \frac{d}{dt} \vec{v}_d = -\mu \nabla_\perp B_g - \mu \vec{b} \cdot \nabla B_g \vec{b} + q \vec{v}_d \times \vec{B}_g$$

$$\downarrow \frac{d}{dt} \vec{b} = \frac{\partial}{\partial t} \vec{b} + \vec{v}_g \cdot \nabla \vec{b}=\frac{\partial}{\partial t} \vec{b} + v_\parallel \vec{b} \cdot \nabla \vec{b} + \vec{v}_d \cdot \nabla \vec{b}$$

$$m \frac{d v_\parallel}{dt} \vec{b} + m v_\parallel (\frac{\partial}{\partial t} \vec{b} + \vec{v}_d \cdot \nabla \vec{b}) + m v_\parallel^2 \vec{b} \cdot \nabla \vec{b} + m \frac{d}{dt} \vec{v}_d = \dots$$

$$\downarrow \cdot \vec{b}$$

$$m \frac{d v_\parallel}{dt} = -\mu \vec{b} \cdot \nabla B_g$$

$$\downarrow \times \vec{b} \quad$$

$$\vec{v}_d = \frac{\mu}{q B_g} \vec{b} \times \nabla_\perp B_g + \frac{m v_\parallel^2}{q B_g} \vec{b} \times (\vec{b} \cdot \nabla \vec{b})（ 梯度漂移 + 曲率漂移 = 磁漂移）$$

$$|\frac{\vec{v}_d}{\vec{v}_c}| \sim |\frac{\frac{m v_\perp^2}{2 B_g} \frac{1}{q B_g} \nabla_\perp B_g}{v_\perp}| \sim |\frac{m v_\perp}{B_g q} \frac{\nabla B_g}{B_g}|\sim |r_c \frac{\nabla B_g}{B_g}| \ll 1 \sim |\frac{r_c}{L_B}|$$

# 极化漂移

电场随时间变化，在电漂移基础上多出一项$\vec{v}_p$
$$\vec{v} = \vec{v}_c + \vec{v}_E + \vec{v}_p$$

$$\vec{v}_E = \frac{\vec{E} \times \vec{B}}{B^2}$$

带入运动方程
$$m \frac{d\vec{v}_c}{dt} + m \frac{d\vec{v}_E}{dt} + m \frac{d\vec{v}_p}{dt} = q \vec{E} + q (\vec{v}_c \times \vec{B}) + q (\vec{v}_E \times \vec{B}) + q (\vec{v}_p \times \vec{B})$$

$$m \frac{d\vec{v}_E}{dt} + m \frac{d\vec{v}_p}{dt} = q \vec{v}_p \times \vec{B}$$

进行量级比较
$$\left| \frac{m \frac{d\vec{v}_p}{dt}}{q \vec{v}_p \times \vec{B}} \right| \sim \left| \frac{\frac{1}{v_p} \frac{d v_p}{dt}}{\omega_c} \right| \sim \ll 1$$

$$
\begin{cases}
m \frac{d\vec{v}_E}{dt} = q \vec{v}_p \times \vec{B}  \\
m \frac{d\vec{E}}{dt} \times \frac{\vec{B}}{B^2} = q \vec{v}_p \times \vec{B} \quad
\end{cases}
$$

$$
\Rightarrow \vec{v}_{p\perp} = -\frac{m}{q B^2} (\frac{d\vec{E}}{dt} \times \vec{B}) \times \vec{B}= \frac{1}{\omega_c B} (\frac{d\vec{E}}{dt})_\perp
$$

极化电流
$$\vec{j}_p = \sum_i n_i q_i \vec{v}_{pi} = \frac{\rho}{B^2} \frac{d\vec{E}_\perp}{dt}$$

$$\left| \frac{\vec{v}_{pe}}{\vec{v}_{pi}} \right| \sim \frac{m_e}{m_i} \ll 1$$
# 缓变磁场漂移

$$m \frac{d\vec{v}}{dt} \cdot \vec{v} = q \vec{E} \cdot \vec{v} + q (\vec{v} \times \vec{B}) \cdot \vec{v}$$

$$\frac{1}{2} m \frac{d}{dt} (v_\parallel^2 + v_\perp^2) = q \vec{E} \cdot \vec{v}$$

$$m v_\parallel \frac{d v_\parallel}{dt} + \frac{d}{dt} (\mu B) = q \vec{E} \cdot \vec{v}$$

$$\downarrow \frac{d v_\parallel}{dt} = \frac{q}{m} E_\parallel - \frac{\mu}{m} \vec{b} \cdot \nabla B_g$$

$$\langle q v_\parallel E_\parallel - \mu v_\parallel \vec{b} \cdot \nabla B + \frac{d\mu}{dt} B + \mu \frac{dB}{dt} \rangle = q v_\parallel E_\parallel + \langle q \vec{E}_\perp \cdot \vec{v}_c \rangle$$

$$\langle \frac{d\mu}{dt} \rangle = -\langle \frac{\mu}{B} \frac{dB}{dt} \rangle + \frac{\mu}{B} v_\parallel \vec{b} \cdot \nabla B + \frac{q}{B} \langle \vec{E}_\perp \cdot \vec{v}_c \rangle$$

$$= -\frac{\mu}{B} \frac{\partial B}{\partial t} + \frac{q}{B} \langle \vec{E}_\perp \cdot \vec{v}_c \rangle \quad \nabla \times \vec{E} = -\frac{\partial \vec{B}}{\partial t}$$

$$= -\frac{\mu}{B} \frac{\partial B}{\partial t} + \frac{q}{B} \frac{\omega}{2\pi} \oint \vec{E}_\perp \cdot d\vec{l} \quad S = \pi r_c^2= \pi (\frac{m v_c}{B q})^2$$

$$= -\frac{\mu}{B} \frac{\partial B}{\partial t} + \frac{q}{B} \frac{\omega}{2\pi} \int \nabla \times \vec{E} \cdot d\vec{S} \quad $$

$$= \frac{q}{B} \frac{\omega}{2\pi} \int (\frac{\partial \vec{B}}{\partial t}+\nabla \times \vec{E}) \cdot d\vec{S}=0$$

即磁矩守恒
# 绝热不变量

$$\begin{cases} q = \theta \\ p = m v_\perp r_c \end{cases} \Rightarrow\oint p dq = \oint m v_\perp r_c d\theta = 2\pi r_c m v_\perp= 4\pi \frac{m}{q} \mu = const$$

$$\Rightarrow \mu = const$$

磁镜中，中心磁场与最大磁场分别为 $B_{min},B_{max}$
$$\mu_0 = \frac{m v_{\perp 0}^2}{2 B_{min}} = \frac{m v_\perp^2}{2 B}$$

$$\frac{v_{\perp 0}}{v_0} = \sin \theta, \quad \theta \text{ 为pitch angle}$$

捕获临界条件 $v_\perp^2 = v_{\perp 0}^2 + v_{\parallel 0}^2$
$$\frac{v_{\perp 0}^2}{B_{min}} = \frac{v_{\perp 0}^2 + v_{\parallel 0}^2}{B_{max}}, \quad \frac{B_{max}}{B_{min}} = 1 + (\frac{v_{\parallel 0}}{v_{\perp 0}})^2$$

$$\sin^2 \theta_c = \frac{B_{min}}{B_{max}} \quad \theta < \theta_c, \text{ 粒子损失}$$

在磁镜中反弹过程中
$$J = \oint v_\parallel ds, \quad |\frac{1}{B} \frac{\partial B}{\partial t} \tau_b| \ll 1$$

无电场时，$K = \frac{1}{2} m v_\parallel^2 + \mu B = const$
$$v_\parallel = \pm (\frac{2}{m} (K - \mu B))^{\frac{1}{2}}$$

纵向绝热不变量
$$J = \oint v_\parallel dl = 2 \int_{l_{b1}}^{l_{b2}} (\frac{2}{m})^{\frac{1}{2}} (K - \mu B)^{\frac{1}{2}} dl$$

$$\frac{1}{2} \frac{dJ}{dt} = (\frac{2}{m})^{\frac{1}{2}} (K - \mu B)^{\frac{1}{2}}\frac{dl}{dt} \Big|_{l_{b1}}^{l_{b2}} + \int_{l_{b1}}^{l_{b2}} \frac{d}{dt} [(\frac{2}{m})^{\frac{1}{2}} (K - \mu B)^{\frac{1}{2}}] dl$$

在反弹点 $(K - \mu B)^{\frac{1}{2}} = 0$

$$= \int_{l_{b1}}^{l_{b2}} \frac{d}{dt} [(\frac{2}{m})^{\frac{1}{2}} (K - \mu B)^{\frac{1}{2}}] dl$$

$$= \int_{l_{b1}}^{l_{b2}} (\frac{2}{m})^{\frac{1}{2}} \frac{1}{2} (K - \mu B)^{-\frac{1}{2}} \frac{d}{dt} (-\mu B) dl$$

$$= \int_{l_{b1}}^{l_{b2}} \frac{1}{m} \cdot \frac{1}{v_\parallel} \frac{d}{dt} (-\mu B) dl$$

$$= \int_{l_{b1}}^{l_{b2}} \frac{1}{m} \frac{1}{v_\parallel} \frac{dl}{dt} \frac{\partial}{\partial l} (-\mu B) dl$$

$$= \int_{l_{b1}}^{l_{b2}} \frac{1}{m} \frac{\partial}{\partial l} (-\mu B) dl = \frac{-\mu B}{m} \Big|_{l_{b1}}^{l_{b2}}$$

$$= 0$$
# 有质动力

$$m_e \frac{d\vec{v}}{dt} = -e [\vec{E}(\vec{r}) + \vec{v} \times \vec{B}(\vec{r})]$$

$\vec{E}_0, \vec{B}_0$ (直流部分) 不考虑，考虑波动 $\vec{E}_1, \vec{B}_1$

$\vec{E}_1 = \vec{E}_s(\vec{r}) \cos \omega t$，初始 $\vec{r}_0$

$$m \frac{d\vec{v}_1}{dt} = -e \vec{E}_s(\vec{r}_0) \cos \omega t \Rightarrow \vec{v}_1 = -\frac{e}{m\omega} \vec{E}_s(\vec{r}_0) \sin \omega t$$

$$\frac{d\vec{r}_1}{dt} = \vec{v}_1, \quad \vec{r}_1 = \frac{e}{m\omega^2} \vec{E}_s(\vec{r}_0) \cos \omega t$$

$$m \frac{d\vec{v}_2}{dt} = -e (\vec{r}_1 \cdot \nabla \vec{E}_1(\vec{r}_0) + \vec{v}_1 \times \vec{B}_1(\vec{r}_0))$$

$$\nabla \times \vec{E} = -\frac{\partial \vec{B}}{\partial t} \Rightarrow \vec{B}_1(\vec{r}_0) = -\frac{1}{\omega} \nabla \times \vec{E}_1 \Big|_{\vec{r}=\vec{r}_0} \sin \omega t$$

$$= -e [\frac{e}{m\omega^2} \vec{E}_s(\vec{r}_0) \cdot \nabla \vec{E}_s(\vec{r}_0) \cos^2 \omega t + \frac{e}{m\omega^2} \vec{E}_s(\vec{r}_0) \times \nabla \times \vec{E}_s(\vec{r}_0) \sin^2 \omega t]$$

在一个波周期内平均
$$m \frac{d}{dt} \langle \vec{v}_2 \rangle = -\frac{e^2}{2 m \omega^2} (\vec{E}_s \cdot \nabla \vec{E}_s + \vec{E}_s \times \nabla \times \vec{E}_s) = \vec{F}_{NL}$$

$$\vec{F}_{NL} = -\frac{e^2}{2 m \omega^2} \cdot \frac{\nabla E_s^2}{2} \quad \omega_{pe}^2 = \frac{n e^2}{m_e \varepsilon_0}$$

单位体积受力
$$\vec{f}_{NL} = -\frac{n e^2}{4 m \omega^2} \nabla E_s^2= -\frac{\omega_{pe}^2}{\omega^2} \frac{\nabla E_s^2}{4 \varepsilon_0}$$
