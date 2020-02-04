# Linear Regression Analysis

## Simple Linear Regression Analysis

### Introduction to Regression Analysis

- 回归分析有两种情况
	- Y是随机变量，X是固定非随机变量
	- X和Y都是随机变量
- 描述性研究和预测性研究
	- 描述：检查X和Y的系数方向和大小，给出X系数的置信区间
	- 预测：给定X值预测Y值，给出Y的预测区间
- 概率模型：$$Y = f(X) + \varepsilon$$
	- 概率模型和数学模型的本质区别就在于随机干扰项
	- 假设检验和构建置信区间都依赖于随机干扰项
	- $$f(X)$$可以是线性或非线性的

### Simple Linear Regression Model

- 模型：$$Y_i = \beta_0 + \beta_1 X_i + \varepsilon_i$$
	- Y是随机变量，$$Var(Y) = Var(\varepsilon) = \sigma^2$$
- 对模型进行估计，记估计的模型为$$\hat{Y} = b_0 + b_1 X$$，$$e_i = Y_i - \hat{Y}_i$$
- 估计方法：最小二乘法
	- 为什么不用最大似然法：因为最小二乘法不需要假定
	- 为什么用最小二乘法：高斯-马尔可夫定理
		- 假定条件：$$E[\varepsilon] = 0$$，$$Var(\varepsilon_i) = \sigma^2$$，$$cov(\varepsilon_i, \varepsilon_j) = 0$$
		- 结论：最小二乘法的估计量是BLUE
	- 最小二乘法估计结果的结论（P12）
- 正态回归模型
	- 原因：为了建立置信区间和进行假设检验，必须对残差的分布进行假定
	- 如果样本够大，可以应用中心极限定理，不需要假设正态

### Inferences in Regression Analysis

- 用统计量$$b_0$$和$$b_1$$对参数$$\beta_0$$和$$\beta_1$$进行推断
	- 均值：b是$$\beta$$的无偏估计
	- 方差：u正态分布，所以Y正态分布，又因为b是Y的线性函数，所以大样本下可以用中心极限定理，b正态分布
- 建立置信区间
	- 均值预测：$$E[Y]$$的置信区间
		- 均值：$$\hat{Y}$$是$$E[Y]$$的无偏估计
		- 方差：$$\hat{Y}$$是b的线性函数，b是u的线性函数，所以大样本下可以用中心极限定理，$$\hat{Y}$$正态分布
	- 个值预测：$$Y_{i(new)}$$的预测区间
		- 均值：$$\hat{Y}$$是$$Y_{i(new)}$$的无偏估计
		- 方差
			- $$Y_{i(new)} = E[Y] + \varepsilon$$，但$$E[Y]$$在哪不知道
			- 最保守的方法是，先建立$$E[Y]$$的置信区间，再假设$$E[Y]$$分别位于置信区间的上下限，以此再构造$$Y_{i(new)}$$的置信区间
			- 后一步依赖于u的正态性假定
- 检验整个模型的显著性
	- 非正式方法：$$R^2$$
	- 正式方法：ANOVA
		- 方差分解：SST = SSR + SSE，即$$\sum{(Y_i - \bar{Y})^2} = \sum{(\hat{Y}_i - \bar{Y})^2} + \sum{(Y_i - \hat{Y}_i)^2}$$
		- 列方差分析表，计算F值
		- 可以将非正式的$$R^2$$变成正式的F检验
- 如果X也是随机的
	- 可以用总体相关系数$$\rho$$衡量X和Y的关系
	- $$\rho$$只反映线性关系
	- 样本相关系数r是总体相关系数$$\rho$$的一个估计量
	- r衡量变量的线性相关强度，$$R^2$$衡量模型的解释力度
	- 假设X和Y服从二元正态分布，可以检验$$\rho=0$$
- 标准化回归系数
	- 标准化X和Y后再做回归
	- 二元情况下标准化回归系数等于相关系数
	- 多元情况下可以比较每个X的贡献

### Diagnostics and Remedial Measures

- 残差分析的逻辑
	- 残差是随机干扰项的一个估计
	- 所以如果模型适当，残差应该和随机干扰项有相似的性质
- 非正式检验
	- 异方差：e对yhat或x的散点图
	- 独立性：时间序列或重复实验中容易发生
	- 正态性：p-p图
	- 线性模型：双变量回归用Y对X做散点图、多元回归用残差对拟合值做散点图 
	- 异常值：各种残差图
- 正式检验（P47）
	- 随机性、自相关、正态性、同方差、欠拟合
- 解决方法
	- 放弃线性模型，用非线性模型
	- 对数据做变换
		- box-cox变换
- 评论
	- 样本的选择究竟是不是随机的？
	- 相关不代表因果

### Matrix Approach to Linear Regression Analysis

### 解释一个模型

- 解释系数
- 解释系数的显著性
- 解释模型的显著性
- 残差分析

## Multiple Regression Analysis (I)

### General Multiple Linear Regression Model

- 形式：$$Y_i = \beta_0 + \beta_1 X_{i1} + \beta_2 X_{i2} + \cdots + \beta_k X_{ik} + \varepsilon_i$$
	- 独立条件太强，不相关即可
	- X的选取：一阶模型、交互作用、二阶模型、多项式模型

### Linear Regression Model in Matrix Terms

### Extimation and Inferences in Matrix Terms

### ANOVA Results

### $$R^2$$ and Adjusted $$R^2$$

- 给定样本数量，解释变量越多$$R^2$$通常越高
- 需要调整$$R^2$$的原因：防止过拟合

### Indicator (Dummy) Variables

- 使用虚拟变量可以在模型中加入定性变量
- 交互作用模型

### Partial F-test

- 只能检验镶嵌模型
	- 镶嵌模型：一个模型中包含另一个模型的全部变量，并至少包含额外的一个变量
	- 一阶模型和二阶模型是镶嵌模型

### Beta (Standardized) Coefficients

- 多元回归中beta系数可以直接比较两个变量的重要程度

### Coefficients of Partial Determination

- 偏判别系数可以衡量新加入一个X的边际贡献
- 计算：$$r^2 = (SSE_{reduced\ model} - SSE_{full\ model})/SSE_{reduced\ model}$$
- 偏判别系数的值在0-1之间，越大说明边际贡献越大
- 偏判别系数可以被解释为简单判别系数（书P270）

### Multicollinearity and Its Effects

- 变量之间的高度相关叫多重共线性
- 后果
	- 模型的系数不稳定
	- 回归结果可能误导
- 如何检验：都是充分非必要条件
	- 变量间的相关系数高
	- F检验显著，但t检验不显著
	- 系数和理论违背
	- VIF>=10
	- 主成分分析
- 解决方法：去掉高度相关的变量

### Polynomial Regression Models

- 为什么用多项式模型
	- 自变量和因变量的关系确实是多项式的
	- 多项式能对关系做更好的近似
- 二阶模型
	- 中心化可以解决多重共线性问题，但更高阶不行
- 高阶模型的问题
	- 多重共线性
	- 系数难以解释

## Multiple Regression Analysis (II)

### Overview of Model-Building Process

### All-Possible-Regressions Procedure

- 从一组模型中选出最终模型
- 指标
	- $$R^2_{p}$$,
	- $$R^2_{a, p}$$,
	- $$C_p = \frac{SSE_p}{MSE(X_1, \dots, X_{P-1})} - (n-2p)$$,
	- $$AIC_p = n\ln{SSE_p} - n\ln{n} + 2p$$,
	- $$SBC_p = n\ln{SSE_p} - n\ln{n} + [\ln{n}]p$$,
	- $$PRESS_p = \sum_{i=1}^n{(Y_i - \hat{Y}_{i(i)})^2}$$,
	- $$C_p$$关注解释，$$PRESS_p$$关注预测
- 先通过指标选出几个好模型，再进一步选择
	- 残差分析、检查有影响力的极值、其他检验、研究者的预期、验模

### Forward Stepwise Regression and Other Automatic Procedures

- 向前方法
	- 开始先向模型中加入和Y相关性最高的一个变量
	- 每次向模型中加入偏F检验最显著的一个变量，直到偏F检验不显著
	- 变量一旦被加入就不会再移除（严进宽出） 
- 向后方法
	- 从全模型开始
	- 每次用偏F检验排除一个变量，直到偏F检验都显著
	- 变量一旦被排除就不会再进入（宽进严出）
- 逐步方法
	- 开始先向模型中加入和Y相关性最高的一个变量
	- 每次向模型中加入偏F检验最显著的一个变量
	- 每当加入一个变量后，对在模型中的每一个变量做偏F检验，排除不显著的变量
- 对自动方法的评论
	- 一次只增加/删除一个变量而不是一组
	- 偏F检验只可以检验镶嵌模型，因此有大量的模型未检验到
	- 所以自动方法可能找到局部最优而非全局最优
- 正确的方法
	- 用自动方法找到最优的自变量个数k
	- 对于k、k+1、k-1，用全模型方法找出最优的自变量组合
- 对模型选择的评论
	- 可以人为指定某些变量在模型中，如果目的是解释
	- 虚拟变量一次要加一组
	- 加入高次项或交互项的同时，要加一次项

### Model Validation

- 验模的方法
	- 收集新数据（没有时效性）
	- 和理论比较（探索性研究还没有理论）
	- 将数据分成两部分验证
		- 指标：$$MSPR = \frac{\sum_{i=1}^{n^*}{(Y_i - \hat{Y}_i)^2}}{n^*}$$
- 评论
	- 最好做double cross-validation
	- 小样本只能用$$PRESS_p$$验模
	- 通过验模选择模型后，再将数据合并到一起做最后的估计

### 从多个模型中选模型

- 排除系数方向相反的
- 排除指标不好的
- 残差分析，排除违背假定的
- 排除验模结果不好的
	- 指标不好
	- 系数方向和大小变化

## Multiple Regression Analysis (III)

### Partial Regression Plots

- 步骤（若检验$$X_k$$是不是有用）
	- Y对所有其他解释变量回归，得到残差$$e_i(Y|X_{-k})$$
	- $$X_k$$对所有其他解释变量回归，得到残差$$e_i(X_k|X_{-k})$$
	- 以$$e_i(Y|X_{-k})$$为纵轴，$$e_i(X_k|X_{-k})$$为横轴作散点图
	- 水平直线说明没有用，斜线说明有用

### Studentized Deleted Residuals

- 关于X的极值对模型影响最大

### Hat Matrix Leverage Values

### DFFITS, Cook's Distance and DFBETAS

- DFFITS
	- 考虑$$\hat{Y}_)i$$和$$\hat{Y}_{i(i)}$$的区别，即单个拟合值受的影响
	- 经验法则：小样本和中等大小样本$$>1$$，大样本$$>2(p/n)^{1/2}$$为极值
- Cook's distance
	- 考虑所有拟合值受的总影响
	- 经验法则：0.1-0.2可以接受，0.5是明显有影响
- DFBETAS
	- 考虑系数受的影响
	- 经验法则：小样本和中等大小样本绝对值$$>1$$，大样本绝对值$$>2/\sqrt{n}$$

### Weighted Least Squares

- 步骤
	1. 估计原始模型，得到残差
	2. 将残差的平方或绝对值对选定的预测子回归
	3. 得到残差平方或绝对值的拟合值，计算权重
	4. 使用权重估计原模型
	5. 如果两次估计的系数有明显变化，可能需要再迭代
- 如果可以重复实验，则可以直接计算给定X下Y的方差







