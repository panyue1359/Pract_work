---
title: spyct
---

- spyct/别名

- spyct/定义

- spyct/异同

- spyct/应用
	 - [Semi-supervised oblique predictive clustering trees](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8101547/)：提供了[源码](https://gitlab.com/TStepi/spyct)
		 - 无标签数据可以影响聚类变量(clustering variables)，通过参数$\omega$控制

		 - 代码中默认clustering_data是target_data，即参数$\omega$取1，无标签数据完全不影响模型构建

		 - 原文提到使用参数 $$\omega$$ 控制无标签数据对模型的影响，但 $$\omega$$ 需要针对每个数据集动态选择，文章指出这是该方法的主要缺点

		 - gitlab代码中，没有提及 $$\omega$$ 这个参数，但feature部分提到了“Handles missing values in the data seamlessly.”，说明似乎可以直接掺杂无标签数据

		 - 发生错误“The above exception was the direct cause of the following exception”，发现是predict部分eval(X)没有转换成ndarray

- spyct/文献
	 - [Semi-supervised oblique predictive clustering trees](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8101547/)：提供了[源码](https://gitlab.com/TStepi/spyct)
id:: 621cd178-9967-4242-8b7a-9c83985416a0
