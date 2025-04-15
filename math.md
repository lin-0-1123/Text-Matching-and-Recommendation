# 公式仿写
1. 模型预测公式：
\[
y_i \approx \beta_0 + \sum_{j=1}^{m} \beta_j \times x_j^i
\]
扩展自变量向量后：
\[
y_i \approx \sum_{j=0}^{m} \beta_j \times x_j^i = \vec{\beta} \cdot \vec{x}_i
\]

2. 最小二乘优化目标：
\[
\hat{\vec{\beta}} = \underset{\vec{\beta}}{\arg \min} L(D, \vec{\beta}) = \underset{\vec{\beta}}{\arg \min} \sum_{i=1}^{n} (\vec{\beta} \cdot \vec{x}_i - y_i)^2
\]

3. 矩阵形式的损失函数：
\[
\begin{align*}
L(D, \vec{\beta}) &= \|X\vec{\beta} - Y\|^2 \\
&= (X\vec{\beta} - Y)^{\top} (X\vec{\beta} - Y) \\
&= Y^{\top}Y - Y^{\top}X\vec{\beta} - \vec{\beta}^{\top}X^{\top}Y + \vec{\beta}^{\top}X^{\top}X\vec{\beta}
\end{align*}
\]

4. 损失函数的梯度：
\[
\begin{align*}
\frac{\partial L(D, \vec{\beta})}{\partial \vec{\beta}} &= \frac{\partial (Y^{\top}Y - Y^{\top}X\vec{\beta} - \vec{\beta}^{\top}X^{\top}Y + \vec{\beta}^{\top}X^{\top}X\vec{\beta})}{\partial \vec{\beta}} \\
&= -2X^{\top}Y + 2X^{\top}X\vec{\beta}
\end{align*}
\]

5. 最优参数解：
\[
\begin{align*}
-2X^{\top}Y + 2X^{\top}X\vec{\beta} &= 0 \\
\Rightarrow X^{\top}X\vec{\beta} &= X^{\top}Y \\
\Rightarrow \vec{\beta} &= (X^{\top}X)^{-1}X^{\top}Y
\end{align*}
\]