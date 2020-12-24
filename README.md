# SHAP学习笔记
## 应用背景
可解释工具可以帮助我们在特征工程当中筛选特征也可以在模型实际应用当中做出清晰的解释

常用的决策树模型（XGBoost、LightGBM、CatBoost）的可解释工具
1. 特征重要性（feature important）
2. ELI5（替换）（整体特征贡献分布）
3. SHAP（整体特征贡献分布和单个样本的特征贡献分布）

以上工具不仅仅局限于树模型，这里主要介绍SHAP在常见决策树模型中的实际使用

## SHAP定义
简单模型（如线性回归）的最好解释是模型本身，因为它们容易理解。而对于复杂模型，往往不容易理解，因此我们需要寻找一个简单的解释模型。SHAP将Shapley值解释表示为一种客家特征归因方法，SHAP将模型的预测值解释为每个输入特征的归因值之和。

SHAP具有三个理想的属性：局部准确性，确实性和一致性（具体可参考【2】）

### SHAP值是唯一一致的个性化特征归因方法
首先先定义一致性：每当我们更改模型以使其更依赖于某个特征时，该特征的归因重要性不应该降低。
和现有归因方法看，SHAP值是唯一一致的个性化特征归因方法（具体可参考【2】）

### 安装SHAP
pip install shap

or

conda install -c conda-forge shap


## 参考
【1】https://shap.readthedocs.io/en/latest/index.html
【2】https://zhuanlan.zhihu.com/p/85791430
【3】http://sofasofa.io/tutorials/shap_xgboost/