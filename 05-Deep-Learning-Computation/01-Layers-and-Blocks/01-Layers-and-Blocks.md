# 自定义神经网络

在 PyTorch 中 Module是一个很重要的概念，任何的一个神经网络或者任何的一个层都应该是 nn.Module 的一个子类。

好处：

1. 通过集成 nn.Module 可以继承到很多好用的函数
2. 如：`__init__` 这个初始化用的函数：需要首先调用父类的初始化函数，完成父类的初始化 `super().__init__`，接下来可以通过 `self.hidden = nn.layer_name_class()` 的方式来定义层，例如 `self.hidden = nn.Linear()` 定义一个全连接层。
3. 如：`forward(self, X)` 函数，用来定义前向传播的过程。该函数的返回值是神经网络的输出
4. `nn.Sequential` 是一个特殊的继承自 nn.Module 的类



`自定义：继承 nn.Moudle 类`

```python
import torch
from torch import nn # neural network = nn
from torch.nn import functional as F

class MLP(nn.Module):
    # 用模型参数声明层。这里，我们声明两个全连接的层
    def __init__(self):
        # 调用`MLP`的父类`Module`的构造函数来执行必要的初始化。
        # 这样，在类实例化时也可以指定其他函数参数，例如模型参数`params`（稍后将介绍）
        super().__init__()
        self.hidden = nn.Linear(20, 256)  # 隐藏层
        self.out = nn.Linear(256, 10)  # 输出层

    # 定义模型的前向传播，即如何根据输入`X`返回所需的模型输出
    def forward(self, X):
        # 注意，这里我们使用ReLU的函数版本，其在nn.functional模块中定义。
        return self.out(F.relu(self.hidden(X)))
```



## nn.Sequential 的实现原理

