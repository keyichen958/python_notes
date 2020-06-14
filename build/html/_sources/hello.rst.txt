
2. Python数据可视化
=======================

很久之前对seaborn有过一些涉及但是没有深入探究，这次有趁着有数据可视化的需求，就好好学一学

Seaborn其实是在matplotlib的基础上进行了更高级的API封装，从而使得作图更加容易，在大多数情况下使用seaborn就能做出很具有吸引力的图，为数据分析提供了很大的便利性。但是应该把Seaborn视为matplotlib的补充，而不是替代物。

2.1 图表风格（style）设置
-------------------------------

>>> # 利用 matplotlib创建一个正弦函数及图表
>>> 
>>> def sinplot(flip=1):
>>>     x = np.linspace(0, 14, 100)
>>> #     fig = plt.figure(figsize=(10,6))
>>>     for i in range(1,7):
>>>         plt.plot(x, np.sin(x + i * .5) * (7 - i) * flip)
>>> 
>>> sinplot()


2.2 sns.set() 设置样式参数
-------------------------------
>>> seaborn.set（context =‘notebook’，style =‘darkgrid’，palette =‘deep’，font =‘sans-serif’，font_scale = 1，color_codes = True，rc = None)

>>> sns.set(style='darkgrid',font_scale=1.5)
>>>
>>> # 利用此方法可以快速设置seaborn的默认风格，当然也可以添加参数设置其他风格
>>> # font_scale：float，单独的缩放因子可以独立缩放字体元素的大小。
>>> 
>>> sinplot()


2.3 set_style() 设置图标风格
-------------------------------
>>> seaborn.set_style（style = None，rc = None )

>>> # 切换seaborn图表风格
>>> # 风格选择包括："white", "dark", "whitegrid", "darkgrid", "ticks"
>>> # rc：dict，可选,参数映射以覆盖预设的seaborn样式字典中的值
>>>
>>> fig = plt.figure(figsize=(10, 8))
>>> 
>>> ax1 = fig.add_subplot(2, 1, 1)
>>> sns.set_style('whitegrid',{"xtick.major.size": 10, "ytick.major.size": 10})
>>> data = np.random.normal(size=(20,6)) + np.arange(6) / 2
>>> sns.boxplot(data=data)
>>>
>>>
>>> ax2 =  fig.add_subplot(2, 1, 2)
>>> sinplot()


