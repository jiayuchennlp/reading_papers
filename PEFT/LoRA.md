### Introdution
-----

现有低资源训练技术的缺点： 
1. 由于插入额外层或者增加输入序列的长度，带来推理延时
2. 通常不能超过finetune baseline，需要在效率和模型质量之间进行权衡

启发： 
1. the learned over-parametrized models in fact reside on a low intrinsic dimension
2. 假设模型适应过程中，权重的变化也有一个较低的“low rank”， 提出LoRA 方法

优点：
1. 存储要求低
2. 训练效率高
3. 无推理延时
4. 与其他方法正交，可结合使用

