---
title: skopt
---

- skopt/官网
	 - [Scikit-Optimizer](https://scikit-optimize.github.io/stable/index.html)( skopt )

	 - [Examples](https://scikit-optimize.github.io/stable/auto_examples/index.html)

- skopt/基础
	 - ((610ee15d-9ffe-41cc-9f1c-9dc97df7ccf5))
		 - 高斯贝叶斯全局寻优，参数设置[参考](https://scikit-optimize.github.io/stable/modules/generated/skopt.utils.use_named_args.html#skopt.utils.use_named_args)
			 - 
``` python
#优化前先fit模型
#可以使用其他先验函数如forest_minimize,gbrt_minimize等
from skopt import gp_minimize
from skopt.space import Integer, Real
space_frac=[Real(0.1,1,name='Al'),Real(0.1,1,name='Co')\
            ,Real(0.1,1,name='Cr'),Real(0.1,1,name='Cu')\
            ,Real(0.1,1,name='Fe'),Real(0.1,1,name='Mn')\
            ,Real(0.1,1,name='Ni'),Real(0.1,1,name='V')]
from skopt.utils import use_named_args
@use_named_args(space_frac)
def ratio_to_pred(Al,Co,Cr,Cu,Fe,Mn,Ni,V,rege=rege):
    atomic=np.array([Al,Co,Cr,Cu,Fe,Mn,Ni,V])
    X_pred=dataset_generator.frac_ele_emp(atomic)
    X_pred=X_pred[frac+ele_candidate+emp_candidate].values
    #加负号使问题转换为找最小值
    return -rege.predict(X_pred)[0]
#绘制优化轮数-目标值图
from skopt.plots import plot_convergence
result=gp_minimize(ratio_to_pred,space_frac,n_calls=100\
                   ,acq_func='EI',random_state=0)
print("x^*=%s, f(x^*)=%.4f" % (result.x, result.fun))
plot_convergence(result)

```

		 - 

	 - ((b6a114d3-182a-47ee-bebb-2af1b7f72f3e))
		 - 不支持离散输入：[Accepting discontinuous sets for a dimension? · Issue #154 · scikit-optimize/scikit-optimize](https://github.com/scikit-optimize/scikit-optimize/issues/154)

		 - [Async optimization Loop](https://scikit-optimize.github.io/stable/auto_examples/ask-and-tell.html#sphx-glr-auto-examples-ask-and-tell-py)：计算与实验流程配合
id:: 6226cd36-a25e-4373-83cb-99ef9dde8810

- skopt/问题

- skopt/文献
	 - [贝叶斯优化的各个python实现包之间有什么区别？ - 知乎](https://www.zhihu.com/question/360767107)

	 - T. Ueno et al. (2016) COMBO: An efficient Bayesian optimization library for materials science，适用于大规模计算

	 - 
