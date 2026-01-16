# Debye 屏蔽（等离子体特征长度）

Poisson 方程
$$\nabla \cdot \vec{E} = \frac{\rho}{\varepsilon_0}，\rho = -e n_e + \sum_\alpha Z_\alpha e n_\alpha$$

$$\nabla^2 \phi = -\frac{\rho}{\varepsilon_0}$$

热平衡下，$n \propto$ Boltzmann 分布
$$n_e = n_{e0} \exp\left(\frac{e\phi}{T_e}\right), \quad n_\alpha = n_{\alpha0} \exp\left(-\frac{Z_\alpha e\phi}{T_\alpha}\right)$$

在远处 $e\phi \ll T_e, \quad Z_\alpha e\phi \ll T_\alpha$，展开得，
$$n_e \sim n_{e0} (1 + \frac{e\phi}{T_e}) \quad n_\alpha \sim n_{\alpha0} (1 - \frac{Z_\alpha e\phi}{T_\alpha})$$

带入Poisson方程，
$$\nabla^2 \phi = e (n_{e0} - \sum_\alpha Z_\alpha n_\alpha + n_{e0} \frac{e\phi}{T_e} + \sum_\alpha n_{\alpha0} \frac{Z_\alpha^2 e\phi}{T_\alpha}) / \varepsilon_0$$

准中性 $n_{e0} e = \sum Z_\alpha n_{\alpha0} e$
$$\nabla^2 \phi = \left(\frac{n_{e0}}{T_e} + \sum_\alpha n_{\alpha0} \frac{Z_\alpha^2}{T_\alpha}\right) \frac{e^2 \phi}{\varepsilon_0} = \frac{\phi}{\lambda_D^2}$$
$\downarrow$

定义$\lambda_D$ (Debye 长度)
$$
\lambda_{D}=\sqrt{ \frac{\varepsilon_{0}}{\left(\frac{n_{e0}}{T_e} + \sum_\alpha n_{\alpha0} \frac{Z_\alpha^2}{T_\alpha}\right)e^{2} } }
$$

若分别假定离子不动或电子不动则可以得到电子德拜长度与离子德拜长度，有以下关系，
$$
\frac{1}{\lambda_{D}^{2}}=\frac{1}{\lambda_{De}^{2}}+\frac{1}{\lambda_{Di}^{2}}
$$

考虑球对称情况
$$\frac{1}{r^2} \frac{d}{dr} (r^2 \frac{d\phi}{dr}) = \frac{\phi}{\lambda_D^2}$$

作变换 $\phi(r) = \frac{u(r)}{r}$
$$\frac{d^2 u(r)}{dr^2} - \frac{u(r)}{\lambda_D^2} = 0
\Rightarrow u(r) = A \exp(-\frac{r}{\lambda_D}) + B \exp(\frac{r}{\lambda_D})$$

$$\phi(r) = \frac{A}{r} \exp(-\frac{r}{\lambda_D}) + \frac{B}{r} \exp(\frac{r}{\lambda_D})$$

考虑边界条件 $r \rightarrow \infty, \phi \rightarrow 0; \quad r \rightarrow 0, \phi \rightarrow \frac{q}{4\pi \varepsilon_0 r}$，得到$A = \frac{q}{4\pi \varepsilon_0}, \quad B = 0$，因此
$$\phi(r) = \frac{q}{4\pi \varepsilon_0 r} \exp(-\frac{r}{\lambda_D})$$

由点电荷的在真空中的反比变为指数衰减，这来源于点电荷吸引异号电荷在其周围形成Debye屏蔽。这要求带电粒子系统特征尺度 $L \gg \lambda_D$（等体判据）。

同时Boltzmann 分布要求球内粒子数很大
$$N_D = n \lambda_D^3 \gg 1, \quad g = \frac{1}{n \lambda_D^3} \ll 1$$

---
# 等体频率（等离子体特征时间）

物理图像：多余电子产生电场 $\rightarrow$ 向外运动 $\rightarrow$ 中性 $\rightarrow$ 惯性形成反向电场 $\rightarrow$ 发生振荡（等体振荡）

假设离子不动，电子位移 $x$
$$\sigma = n_e e x, \quad E = \sigma / \varepsilon_0 = n_e e x / \varepsilon_0$$

$$m_e \frac{d^2 x}{dt^2} = -e E = -\frac{n_e e^2 x}{\varepsilon_0}$$

$$\frac{d^2 x}{dt^2} + \omega_{pe}^2 x = 0 \quad \omega_{pe} = \sqrt{\frac{n_e e^2}{\varepsilon_0 m_e}}$$

离子同样有，
$$\omega_{pi} = \sqrt{\frac{n_i Z_i e^2}{\varepsilon_0 m_i}} \quad m_i \gg m_e, \quad \omega_{pe} \gg \omega_{pi}$$

电子离子同时考虑，约化质量 $m = \frac{m_e m_i}{m_e + m_i}$
$$\omega_p^2 = \frac{n e^2}{\varepsilon_0 m} = \frac{n e^2}{\varepsilon_0} \frac{m_e + m_i}{m_e m_i} = \omega_{pe}^2 + \omega_{pi}^2 \sim \omega_{pe}^2$$

等体频率与德拜长度的关系：
$$\lambda_{de} = \frac{v_{the}}{\omega_{pe}} = \frac{\sqrt{\frac{T_e}{m_e}}}{\sqrt{\frac{n e^2}{\varepsilon_0 m_e}}} = \sqrt{\frac{\varepsilon_0 T_e}{n e^2}}$$

电子的震荡运动方程：$$x(t) = a \cos(\omega_{pe} t + \alpha)$$振荡能量 $\frac{1}{2} m_e (a \omega_{pe})^2$

由热能转化 $\frac{1}{2} m_e (a \omega_{pe})^2 = \frac{1}{2} k T_e$

$$a = \sqrt{\frac{T_e}{m}} \cdot \frac{1}{\omega_{pe}} = \lambda_{de}$$

振荡区域在 $\lambda_{De}$ 量级，说明在Debye球内可以产生电荷分离。

$$t_d = \frac{\lambda_{de}}{v_{the}} = \frac{1}{\omega_{pe}}$$

等体响应时间

综合可以得到等体介质条件：
$$L \gg \lambda_D, \quad g = \frac{1}{n \lambda_D^3} \ll 1, \quad \tau \gg t_d$$

---

