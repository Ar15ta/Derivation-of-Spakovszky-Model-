
|  属性  |            [[法术表]]             |              |             |                          |
| :--: | :----------------------------: | ------------ | ----------- | ------------------------ |
|  关联  | [[Spakovszky稳定性方法——模型Ⅱ——轴流转子]] | [[涡量、旋度恒等式]] | [[叶轮机械总参数]] | [[Spakovszky稳定性方法——模型Ⅰ]] |
| 链接解释 |       差不多，都是用匹配条件建立传递矩阵        | 又用           | 出现其中的定义     | 复用非定常总压降，但是速度变成相对速度      |
***
# $Model\space Ⅱ$
    激动的盘。

| 变量名                 | 符号                     | 单位          | 量纲               | 说明                                       |
| ------------------- | ---------------------- | ----------- | ---------------- | ---------------------------------------- |
| 绝对速度                | $\mathbf{v}$           | $\text{m/s}$ | $L T^{-1}$       | 静止坐标系下的速度                              |
| 相对速度                | $\mathbf{w}$           | $\text{m/s}$ | $L T^{-1}$       | 随叶轮旋转的坐标系下的速度                         |
| 叶轮角速度矢量             | $\boldsymbol{\Omega}$  | $\text{rad/s}$ | $T^{-1}$         | 大小 $\Omega$，方向沿旋转轴                     |
| 位置矢量                | $\mathbf{r}$           | $\text{m}$     | $L$              | 从旋转中心指向质点                               |
| 绝对涡量                | $\boldsymbol{\omega}_a = \nabla \times \mathbf{v}$ | $\text{s}^{-1}$ | $T^{-1}$         | 绝对坐标系下的涡量                              |
| 相对涡量                | $\boldsymbol{\omega}_r = \nabla \times \mathbf{w}$ | $\text{s}^{-1}$ | $T^{-1}$         | 旋转坐标系下的涡量                              |
| 相对涡量轴向分量           | $\omega_x$             | $\text{s}^{-1}$ | $T^{-1}$         | 旋转轴方向的分量（这里 $x$ 轴为轴向）                  |
| 叶轮出口半径             | $R_2$                  | $\text{m}$     | $L$              | 叶轮出口平均半径                               |
| 叶轮出口圆周速度           | $U_2 = \Omega R_2$     | $\text{m/s}$ | $L T^{-1}$       | 叶片出口处的切向速度（理想无滑移）                      |
| 叶轮出口通道宽度           | $b$                    | $\text{m}$     | $L$              | 垂直于叶片表面的通道宽度                           |
| 叶片总数                | $N$                    | –              | 1                | 主叶片 + 分叶片（若有）                          |
| 出口叶片金属角（后弯角）      | $\chi_2$               | $\text{rad}$   | 1                | 叶片出口切线与圆周切线之间的夹角，通常 $0 \le \chi_2 \le 90^\circ$ |
| 滑移速度（大小）           | $v_s$                  | $\text{m/s}$ | $L T^{-1}$       | $U_2 - v_{\theta 2}$，方向与旋转相反              |
| 滑移因子                | $\sigma_W$             | –              | 1                | $\sigma_W = v_{\theta 2} / U_2$           |

***
# 主体
![[Spakovszky稳定性方法——模型Ⅱ——离心转子配图.png]]
# 1. 相对涡量的导出
设叶轮以恒定角速度 $\boldsymbol{\Omega} = \Omega\,\hat{\mathbf{e}}_x$ 绕 $x$ 轴旋转（轴向）。在旋转坐标系中，绝对速度 $\mathbf{v}$ 与相对速度 $\mathbf{w}$ 的关系为：
$$
\mathbf{v} = \mathbf{w} + \boldsymbol{\Omega} \times \mathbf{r}
$$
对等式两边取旋度（在绝对坐标系中运算）：
$$
\nabla \times \mathbf{v} = \nabla \times \mathbf{w} + \nabla \times (\boldsymbol{\Omega} \times \mathbf{r})
$$
利用矢量恒等式 $\nabla \times (\boldsymbol{\Omega} \times \mathbf{r}) = 2\boldsymbol{\Omega}$（$\boldsymbol{\Omega}$ 为常矢量），得：
$$
\boldsymbol{\omega}_a = \boldsymbol{\omega}_r + 2\boldsymbol{\Omega}
$$
其中 $\boldsymbol{\omega}_a = \nabla \times \mathbf{v}$，$\boldsymbol{\omega}_r = \nabla \times \mathbf{w}$。
**进口条件**：假设叶轮上游流动无旋、无粘、不可压，则绝对涡量守恒且初始为零，故 $\boldsymbol{\omega}_a = \mathbf{0}$ 在整个流场成立。
代入上式：
$$
\mathbf{0} = \boldsymbol{\omega}_r + 2\boldsymbol{\Omega}
\quad\Rightarrow\quad
\boldsymbol{\omega}_r = -2\boldsymbol{\Omega}
$$
取轴向分量（$x$ 方向）：
$$
\boxed{\omega_x = -2\Omega} \tag{1}
$$
# 2. Stodola 滑移模型
## 2.1 假想涡与滑移速度
Stodola 假设在叶片出口处存在一个**假想的刚体旋转涡**（eddy），直径等于出口通道宽度 $b$，涡量为 $\omega_x$。涡边缘的周向速度 $v_p$ 满足：
$$
v_p \cdot (\text{周长}) = \omega_x \cdot (\text{面积})
$$
取周长为 $\pi b$，面积为 $\pi (b/2)^2 = \pi b^2/4$，得：
$$
v_p \cdot \pi b = \omega_x \cdot \frac{\pi b^2}{4}
\quad\Rightarrow\quad
v_p = \frac{\omega_x b}{4}
$$
**滑移速度** $v_s$ 定义为该边缘速度，方向与旋转相反：
$$
v_s = v_p = \frac{\omega_x b}{4}
$$
## 2.2 通道宽度几何关系
从叶轮出口几何配图看，可得通道宽度：
$$
b = \frac{2\pi R_2}{N} \cos \chi_2 \tag{2}
$$
其中 $2\pi R_2/N$ 为叶片间距，乘以 $\cos\chi_2$ 得到垂直于叶片的实际宽度。
## 2.3 代入相对涡量
将 $\omega_x = -2\Omega$ 和 $b$ 代入 $v_s$：
$$
v_s = \frac{-2\Omega}{4} \cdot \frac{2\pi R_2}{N} \cos \chi_2
      = -\frac{\pi \Omega R_2}{N} \cos \chi_2
      = -\pi U_2 \frac{\cos \chi_2}{N}
$$
负号表示 $v_s$ 与 $U_2$ 方向相反。
## 2.4 滑移因子定义
滑移因子定义为：
$$
\sigma_W = \frac{v_{\theta 2}}{U_2}
$$
实际出口绝对切向速度 $v_{\theta 2} = U_2 + v_s$，因此：
$$
\sigma_W = 1 + \frac{v_s}{U_2}
      = 1 - \frac{\pi \cos \chi_2}{N} \tag{3}
$$
此即 **Stodola 滑移因子公式**。
## 2.5 常用滑移因子公式
这里既然已经通过滑移因子的方式把后掠角的影响考虑进来，后面

| 作者      | 公式                                                  | 适用范围                        |
| ------- | --------------------------------------------------- | --------------------------- |
| Stodola | $\sigma_W = 1 - \dfrac{\pi \cos\chi_2}{N}$          | 小后弯角（$\chi_2 \le 45^\circ$） |
| Wiesner | $\sigma_W = 1 - \dfrac{\sqrt{\cos\chi_2}}{N^{0.7}}$ | 广泛适用，经验拟合                   |
| Stanitz | $\sigma_W = 1 - \dfrac{1.98}{N}$                    | 径向叶片（$\chi_2 = 0^\circ$）    |

# 3.旋转总压守恒
假设旋转总压（Rotary Stagnation Pressure）
$$
p^* = p_t - \rho \Omega R v_\theta
$$
沿流线守恒。$p_t = p + \frac{1}{2}\rho v^2$ 为绝对总压，$\Omega$ 为叶轮角速度，$R$ 为半径，$v_\theta$ 为绝对切向速度。

在叶轮进口（STA1）和出口（STA2）处分别写出：
$$
p_{t1} - \rho \Omega R_1 v_{\theta1} = p_{t2} - \rho \Omega R_2 v_{\theta2}
$$
移项：
$$
p_{t2} - p_{t1} = \rho \Omega (R_2 v_{\theta2} - R_1 v_{\theta1})
$$
两边除以 $\rho U_2^2$，其中 $U_2 = \Omega R_2$：
$$
\frac{p_{t2} - p_{t1}}{\rho U_2^2} = \frac{\Omega (R_2 v_{\theta2} - R_1 v_{\theta1})}{(\Omega R_2)^2}
= \frac{v_{\theta2}}{\Omega R_2} - \frac{R_1}{R_2}\cdot\frac{v_{\theta1}}{\Omega R_2}
$$
注意到 $\frac{v_{\theta2}}{\Omega R_2} = \frac{v_{\theta2}}{U_2}$，正是出口处的无量纲切向速度，记作 $\hat v_{\theta2}$；同样 $\frac{ v_{\theta1}}{\Omega R_2} = \frac{v_{\theta1}}{U_2}$ 也是无量纲量，记作 $\hat v_{\theta1}$。因此：
$$
\boxed{\hat \psi_I = \hat v_{\theta 2} - \frac{R_1}{R_2} \hat v_{\theta 1}}\tag{4}
$$
# 4. 非定常总压降
在离心叶轮中，叶片通道长且弯曲，流体微团沿流线运动时存在明显的非定常加速度。这部分加速度对应的惯性力需要由叶片做功来提供（或反之，阻碍流动变化），表现为总压的额外变化。该修正用于连接 **稳态等熵总压升**（由欧拉方程给出）与 **实际总压升**（计入损失和非定常惯性）。

在 **相对坐标系** 中，沿一条流线 $s$（从进口 $s1$ 到出口 $s2$）积分非定常加速度，得到的总压降为：
$$
\Delta p_{t,\text{unsteady}} = -\int_{s1}^{s2} \left( \frac{\partial}{\partial t}\bigg|_{\text{rel}} \right) W\, ds
$$
其中：
- $W$ —— 相对速度的大小（有量纲，$\text{m/s}$）；
- $\tau = t \, U_2 / R_2$ —— 无量纲时间，以叶轮出口轮缘速度 $U_2 = \Omega R_2$ 和出口半径 $R_2$ 为参考；
- $\frac{\partial}{\partial\tau}\big|_{\text{rel}}$ —— 在旋转坐标系中观察的当地时间导数。
## 4.1 坐标变换：绝对坐标系中的表达
在小扰动分析中，扰动通常是在**绝对坐标系**中描述的。旋转坐标系与绝对坐标系的时间导数关系为：
$$
\frac{\partial}{\partial\tau}\bigg|_{\text{rel}} = \frac{\partial}{\partial t}\bigg|_{\text{abs}} + \Omega \frac{\partial}{\partial\theta}\bigg|_{\text{abs}}
$$
其中 $\theta$ 为周向坐标，$\frac{\partial}{\partial\theta}$ 项来源于旋转角速度 $\Omega$ 带来的效应。

如果两边都用$U_2$和$R_2$无量纲化，就有：
$$
\frac{\partial}{\partial\tau}\bigg|_{\text{rel}} = \frac{\partial}{\partial\tau}\bigg|_{\text{abs}} +\frac{\partial}{\partial\hat\theta}\bigg|_{\text{abs}}
$$
因此，非定常惯性总压降可写作：
$$
\boxed{
\Delta P_{t,\text{unsteady}} = -\int_{\hat s_1}^{\hat s_2} \left( \frac{\partial}{\partial\tau} + \frac{\partial}{\partial\hat\theta} \right) \hat W \, d\hat s \tag{5}
}
$$

在离心叶轮中，我们希望将分布积分简化为一个集总表达式，仅依赖于 **出口径向速度 $V_{r2}$**（无量纲）。这需要利用 **质量守恒（连续性方程）** 沿流管建立 $W(s)$ 与 $V_{r2}$ 的关系。
## 4.2 流管视角
基本假设：
- 流动沿流管一维化（截面上参数均匀）
- 流管截面积 $A(s)$ 定义为 **垂直于当地流线** 的横截面积
- 流管壁面为流线，无流体穿越
- 允许密度变化，但沿流线 $s$ 的密度分布 $\rho(s)$ 视为已知（从平均流计算或状态方程得到）

通过流管任意截面的 **质量流量** 为常数：
$$
\dot m = \rho(s) \, W(s) \, A(s) = \text{常数} \tag{6}
$$
其中：
- $W(s)$ —— 相对速度的大小（方向沿流线，因而垂直于 $A(s)$）
- $A(s)$ —— 垂直于流线的流管横截面积
- $\rho(s)$ —— 当地密度

在叶轮 **出口**（下标 2），我们通常采用 **径向截面**（法向沿径向）来度量流量。径向截面的质量为：
$$
\dot m = \rho_2 \, V_{r2} \, A_{2,\text{radial}} \tag{7}
$$
其中：
- $V_{r2}$ —— 出口径向速度
- $A_{2,\text{radial}}$ —— 出口处垂直于径向的环形面积（例如 $2\pi R_2 b_2$）

由于质量守恒，式 (1) 与 (2) 相等：

$$
\rho(s) \, W(s) \, A(s) = \rho_2 \, v_{r2} \, A_{2,\text{radial}} \tag{8}
$$
解得：
$$
W(s) = \frac{\rho_2 \, A_{2,\text{radial}}}{\rho(s) \, A(s)} \, v_{r2} \tag{9}
$$
定义 **面积‑密度比** 沿流线的分布，跟前面的系列不一样，这里$s$不是拉普拉斯变量，而是相对流线位置：
$$
AR(s) \equiv \frac{\rho_2 \, A_{2,\text{radial}}}{\rho(s) \, A(s)} \tag{10}
$$
顺带地把无量纲表达式给出来：
$$
\boxed{\hat W(s) = AR(\hat s) \cdot \hat v_{r2}} \tag {11}
$$
代回式(5)：
$$
\Delta P_{t,\text{unsteady}} = -\int_{\hat s_1}^{\hat s_2} \left( \frac{\partial}{\partial\tau} + \frac{\partial}{\partial\hat \theta} \right) \bigl( AR(\hat s) \, \hat v_{r2}(\tau,\hat \theta) \bigr) \, d\hat s
$$

由于偏导数只作用于 $\hat v_{r2}$，可以提到积分号外：
$$
\Delta P_{t,\text{unsteady}} = -\left( \frac{\partial}{\partial\tau} + \frac{\partial}{\partial\theta} \right) \hat v_{r2} \; \cdot \; \int_{\hat s_1}^{\hat s_2} AR(\hat s) \, \hat ds
$$

为了搞定这个积分，我们令：

$$
\lambda_{\text{imp}} = \int_{\hat s_1}^{\hat s_2} AR(\hat s) \, d\hat s \tag{12}
$$
设：
$$
\rho(s)A(s) = \rho_1 A_{1} + k\,(s - s_1), \qquad k = \frac{\rho_2 A_{2,\text{radial}} - \rho_1 A_{1}}{s_{\text{imp}}}
$$
其中，平均的流道长度$\hat s_{\text{imp}} = \hat s_2 - \hat s_1$。

将 $\rho(s)A(s)$ 代入 $AR(s)$ 表达式：
$$
AR(s) = \frac{\rho_2 A_{2,\text{radial}}}{\rho_1 A_{1} + k\,(s - s_1)} \tag{13}
$$
使用换元法，令 $\xi = s - s_1$，则 $\xi \in [0, s_{\text{imp}}]$，分母记作 $a + k\xi$，其中$a = \rho_1 A_{1}$：


于是：
$$
\lambda_{\text{imp}} = \int_0^{s_{\text{imp}}} \frac{\rho_2 A_{2,\text{radial}}}{a + k\xi} \, d\xi
$$
积分基本公式 $\int \frac{d\xi}{a+k\xi} = \frac{1}{k}\ln(a+k\xi)$，故：
$$
\lambda_{\text{imp}} = \rho_2 A_{2,\text{radial}} \cdot \frac{1}{k} \left[ \ln(a+k\xi) \right]_0^{s_{\text{imp}}}
$$
代入 $\xi = s_{\text{imp}}$：$a + b s_{\text{imp}} = \rho_2 A_{2,\text{radial}}$；$\xi = 0$：$a = \rho_1 A_{1}$。因此：
$$
\lambda_{\text{imp}} = \frac{\rho_2 A_{2,\text{radial}}}{k} \ln\left( \frac{\rho_2 A_{2,\text{radial}}}{\rho_1 A_{1}} \right)
$$
将 $k = \frac{\rho_2 A_{2,\text{radial}} - \rho_1 A_{1}}{s_{\text{imp}}}$ 代入：

$$
\lambda_{\text{imp}} = \rho_2 A_{2,\text{radial}} \cdot \frac{s_{\text{imp}}}{\rho_2 A_{2,\text{radial}} - \rho_1 A_{1}} \cdot \ln\left( \frac{\rho_2 A_{2,\text{radial}}}{\rho_1 A_{1}} \right)\tag{14}
$$

定义 **总面积‑密度比**（进口到出口）：
$$
AR_{\text{imp}} = \frac{\rho_2 A_{2,\text{radial}}}{\rho_1 A_{1}}
$$
代入上式：
$$
\lambda_{\text{imp}} = s_{\text{imp}} \cdot \frac{AR_{\text{imp}} \ln(AR_{\text{imp}})}{AR_{\text{imp}} - 1}\tag{15}
$$
所以:
$$
\Delta P_{t,\text{unsteady}} = -\lambda_{\text{imp}}\left( \frac{\partial \hat v_{r2}}{\partial\tau} + \frac{\partial \hat v_{r2}}{\partial\theta} \right) 
$$
上式中的面积计算方式如下：
$$
A_1 =h_1\cdot\frac{2\pi R_1}{N_{main}}\qquad{\space}\qquad{\space}
A_2 =h_2\cdot\left(\frac{2\pi R_2}{N_{main}+N_{splitter}}-t_{imp}\right)
$$
这里$h$是叶高、$N$是叶片数量、$t_{imp}$是叶片尾缘的厚度。这很明显的近似，入口处咱就没考虑叶片厚度。开心可以把前缘厚度也算上的。另外，这里直接用的环形面积，其实也可以采用流道真实面积，多乘一个$cos\chi$就好。
# 5. 匹配条件
由连续性得到：
$$
\hat v_{x1}=AR_{\text{imp}}\hat v_{r2}\tag{16}
$$
由滑移因子得到：
$$
\hat v_{\theta2}=\sigma_W+\hat v_{r2}\cdot\tan\chi_2=1+\hat v_{r2}\cdot tan\beta_2\tag{17}
$$
这里的1是因为圆周速度$R_2\Omega$被归一化了(这里的归一化标准也和前面几份文档的不一样，使用时务必统一），还有注意金属角和气流角不同。

结合式(4)和式(17)，考虑上我们的损失和非定常需要的额外总压降，我们有：
$$
\hat p_{t2}-\hat p_{t1}=1+\hat v_{r2}\cdot\tan\beta_2-\frac{R1}{R2}\hat v_{x1}\cdot \tan\alpha_1 -\hat l_{imp} -\lambda_{imp}\left( \frac{\partial}{\partial\tau} + \frac{\partial}{\partial\theta} \right)\hat v_{r2}\tag{18}
$$

和轴流转子一样，这里的损失可以表示成：
$$
\left[1+\tau_{imp }\cdot\left(\frac{\partial}{\partial \tau}+\frac{\partial}{\partial\hat\theta}\right)\right]\hat l_{imp}=l_{imp}^{ss}(tan\beta_1)\tag{19}
$$
类似地，这里的一阶迟滞估算由下式给出：
$$
\tau_{imp}=\tau_u\cdot\frac{2s_{imp}}{\hat{W}_1+\hat{W}_2}\tag{20}
$$
# 6. 小扰动
## 6.1 传递式展开
展开式（18）的总压：
$$
\hat p_{2}+\frac{1}{2}\hat v_{\theta 2}^2+\frac{1}{2}\hat v_{r 2}^2
-\hat p_{1}-\frac{1}{2}\hat v_{\theta 1}^2-\frac{1}{2}\hat v_{x 1}^2
=
1+\hat v_{r2}\cdot\tan\beta_2-\frac{R1}{R2}\hat v_{x1}\cdot \tan\alpha_1 -\hat l_{imp} -\lambda_{imp}\left( \frac{\partial}{\partial\tau} + \frac{\partial}{\partial\theta} \right)\hat v_{r2}
$$
# 6.2 线性化
进行线性化：
$$
\hat p_{2}+\hat {\overline v}_{\theta 2}\delta\hat v_{\theta 2}+\hat {\overline v}_{r 2}\delta\hat v_{r 2}
-\hat p_{1}-\hat {\overline v}_{\theta 1}\delta\hat v_{\theta 1}-\hat {\overline v}_{x 1}\delta\hat v_{x 1}
=
\delta\hat v_{r2}\cdot\tan\beta_2-\frac{R1}{R2}\delta\hat v_{x1}\cdot \tan\alpha_1 -\delta\hat l_{imp} -\lambda_{imp}\left( \frac{\partial}{\partial\tau} + \frac{\partial}{\partial\theta} \right)\delta\hat v_{r2}
$$
然后，我们只希望保留$\hat v_{x1}$和$\hat v_{r2}$作为传递关系，所以利用前面的速度三角形关系做点变换：
$$
\hat p_{2}+\frac{\hat {\overline v}_{\theta 2}\tan{\beta_2}}{AR_{imp}}\delta\hat v_{x 1}+\frac{\hat {\overline v}_{r 2}}{AR_{imp}}\delta\hat v_{x 1}
-\hat p_{1}-\hat {\overline v}_{\theta 1}\delta\hat v_{\theta 1}-\hat {\overline v}_{x 1}\delta\hat v_{x 1}
=
\frac{\tan\beta_2}{AR_{imp}}\delta\hat v_{x1}-\frac{R1}{R2}\delta\hat v_{x1}\cdot \tan\alpha_1 -\delta\hat l_{imp} -\frac{\lambda_{imp}}{AR_{imp}}\left( \frac{\partial}{\partial\tau} + \frac{\partial}{\partial\theta} \right)\delta\hat v_{x1}
$$
这样我们就完全消除了得到$\hat p_2$式中所需的所有“激盘出口参数”，让我们取拉普拉斯变换，在周向进行傅里叶展开，并把视角聚焦到第$n$阶谐波上，同样$e^{jn\theta}$暂时约掉，重构物理场时再拿回来，有：
$$
\delta\tilde P_{2}+\frac{\hat {\overline v}_{\theta 2}\tan{\beta_2}}{AR_{imp}}\delta\tilde V_{x 1}+\frac{\hat {\overline v}_{r 2}}{AR_{imp}}\delta\tilde V_{x 1}
-\delta\tilde P_{1}-\hat {\overline v}_{\theta 1}\delta\tilde V_{\theta 1}-\hat {\overline v}_{x 1}\delta\tilde V_{x 1}
=
\frac{\tan\beta_2}{AR_{imp}}\delta\tilde V_{x1}-\frac{R1}{R2}\delta\tilde V_{x1}\cdot \tan\alpha_1 -\delta\tilde L_{imp} -\frac{\lambda_{imp}}{AR_{imp}}\left( s+jn\right)\delta\tilde V_{x1}
$$
损失项可以直接用轴流转子的解：
$$
\delta\tilde{L}_R =  \frac{d\hat{l}_{imp}^{ss}}{d\tan\beta_1}\bigg|_{\text{avg}}\cdot \frac{   \delta\tilde{V}_{\theta1} - \tan\beta_1 \delta\tilde{V}_{x1}} {\hat{\overline v}_{x1}[1 + \tau_{imp}(s+jn)]}
$$
这里和轴流转子不一样的地方在于，参考的解变成（链式法则）：
$$
\frac{d\hat{l}_{imp}^{ss}}{d\tan\beta_1}\bigg|_{\text{avg}}
=
\frac{d\hat{l}_{imp}^{ss}}{d\hat{\overline v}_{r2}}\cdot\frac{R_1}{R_2}\frac{1}{(\tan{\alpha_1}-\tan{\beta_1})^2AR_{imp}}
$$
这样，整个式子就变成：
$$
\delta\tilde P_{2}+\frac{\hat {\overline v}_{\theta 2}\tan{\beta_2}}{AR_{imp}}\delta\tilde V_{x 1}+\frac{\hat {\overline v}_{r 2}}{AR_{imp}}\delta\tilde V_{x 1}
-\delta\tilde P_{1}-\hat {\overline v}_{\theta 1}\delta\tilde V_{\theta 1}-\hat {\overline v}_{x 1}\delta\tilde V_{x 1}
=
\frac{\tan\beta_2}{AR_{imp}}\delta\tilde V_{x1}-\frac{R1}{R2}\delta\tilde V_{x1}\cdot \tan\alpha_1 - \frac{d\hat{l}_{imp}^{ss}}{d\tan\beta_1}\bigg|_{\text{avg}}\cdot \frac{   \delta\tilde{V}_{\theta1} - \tan\beta_1 \delta\tilde{V}_{x1}} {\hat{\overline v}_{x1}[1 + \tau_{imp}(s+jn)]} -\frac{\lambda_{imp}}{AR_{imp}}\left( s+jn\right)\delta\tilde V_{x1}\tag{21}
$$
# 7. 传递矩阵
输入向量（进口 STA 1）：  
$$
\begin{bmatrix} \delta\hat V_{r2} \\ \delta\hat V_{\theta2} \\ \delta\hat P_2 \end{bmatrix}(\hat\theta,s)
=
\sum_{n=0}^\infty\mathbb{B}_{\text{imp},n}\cdot e^{jn\theta}\cdot\begin{bmatrix} \delta\tilde V_{x1} \\ \delta\tilde V_{\theta1} \\ \delta\tilde P_1 \end{bmatrix}(s)
$$

传递矩阵：
$$
\boxed{
\mathbb{B}_{\text{imp},n} =
\begin{bmatrix}
\dfrac{1}{AR_{\text{imp}}} & 0 & 0 \\
\dfrac{\tan\beta_2}{AR_{\text{imp}}} & 0 & 0 \\
B_{31} & B_{32} & 1
\end{bmatrix}
}
$$
其中
$$
\begin{aligned}
B_{31} &= \frac{\tan\beta_2-\lambda_{\text{imp}}(s+jn)-\hat{\overline v}_{r2} - \hat{\overline v}_{\theta2}\tan\beta_2}{AR_{\text{imp}}}
        - \frac{R_1}{R_2}\tan\alpha_1
        - \hat{\overline v}_{x1}
        + K_{\text{imp}}\tan\beta_1,\\
B_{32} &= \hat{\overline v}_{\theta1} - K_{\text{imp}},\\
K_{\text{imp}} &= \frac{1}{\hat{\overline v}_{x1}}\,
            \frac{d\hat l_{\text{imp}}^{ss}}{d\tan\beta_1}\bigg|_{\text{avg}}
                \frac{1}{1 + \tau_{\text{imp}}(s+jn)}
\end{aligned}
$$
# 8. 代码
```python
import numpy as np

def B_impeller_n(s, n, AR_imp, R1_R2, tan_beta1, tan_beta2, tan_alpha1,
                 Vx_bar1, Vr_bar2, Vtheta_bar1, Vtheta_bar2,
                 lambda_imp, tau_imp, dL_dtanbeta1):
    """
    离心转子/叶轮执行盘的第 n 阶谐波传递矩阵 (3x3)

    参数
    ----------
    s : complex
        拉普拉斯变量（无量纲）
    n : int
        周向谐波数 (n >= 0)
    AR_imp : float
        叶轮面积-密度比 = (ρ₂A₂)/(ρ₁A₁)
    R1_R2 : float
        叶轮进口半径与出口半径之比 R1/R2
    tan_beta1 : float
        进口相对气流角的正切（平均值）
    tan_beta2 : float
        出口相对气流角的正切（常数）
    tan_alpha1 : float
        进口绝对气流角的正切（平均值）
    Vx_bar1 : float
        进口平均轴向速度（无量纲）
    Vr_bar2 : float
        出口平均径向速度（无量纲）
    Vtheta_bar1 : float
        进口平均周向速度（无量纲）
    Vtheta_bar2 : float
        出口平均周向速度（无量纲）
    lambda_imp : float
        叶轮惯性系数
    tau_imp : float
        损失时间滞后常数（无量纲）
    dL_dtanbeta1 : complex or float
        稳态损失对 tan(beta1) 的偏导数，在工作点取值

    返回
    -------
    B : 3x3 complex array
        离心转子传递矩阵
    """
    # 辅助计算 K_imp
    denom = 1.0 + tau_imp * (s + 1j * n)
    K_imp = dL_dtanbeta1 / (Vx_bar1 * denom)

    # 矩阵行
    row1 = [1.0 / AR_imp, 0.0, 0.0]
    row2 = [tan_beta2 / AR_imp, 0.0, 0.0]

    B31 = (Vx_bar1
           - (Vr_bar2 + Vtheta_bar2 * tan_beta2) / AR_imp
           + tan_beta2 / AR_imp
           - R1_R2 * tan_alpha1
           - lambda_imp * (s + 1j * n) / AR_imp
           + K_imp * tan_beta1)

    B32 = Vtheta_bar1 - K_imp

    row3 = [B31, B32, 1.0]

    B = np.array([row1, row2, row3], dtype=complex)
    return B


# 使用示例
if __name__ == "__main__":
    s = 0.1 + 0.2j
    n = 2
    AR_imp = 1.15
    R1_R2 = 0.7
    tan_beta1 = 0.4
    tan_beta2 = 0.5
    tan_alpha1 = 0.2
    Vx_bar1 = 0.5
    Vr_bar2 = 0.3
    Vtheta_bar1 = 0.3
    Vtheta_bar2 = 0.6
    lambda_imp = 0.8
    tau_imp = 0.15
    dL_dtanbeta1 = 0.1

    B = B_impeller_n(s, n, AR_imp, R1_R2, tan_beta1, tan_beta2, tan_alpha1,
                     Vx_bar1, Vr_bar2, Vtheta_bar1, Vtheta_bar2,
                     lambda_imp, tau_imp, dL_dtanbeta1)
    print("B_impeller_n =\n", B)
```