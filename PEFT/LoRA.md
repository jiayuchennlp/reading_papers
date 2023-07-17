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


### Related Work
-----
现有两类方法：
1. 添加Adapter Layers: 带来推理延时
2. 优化input layer activations： 难以直接优化

### Method
----
<div align=center>
<img src=https://github.com/jiayuchennlp/reading_papers/blob/main/PEFT/pictures/LoRA-1.png/>
</div>

$$h = W_0x + \Delta Wx =  W_0x + AB$$


### Experiments
---
baseline
1. Fine-Tuning(FT)
2. Bias-only or BitFit : only train the bias vectors
3. Prefix-embedding tuning (PreEmbed): inserts special tokens among the input tokens
4. Prefix-layer tuning (PreLayer): learn the activations after every Transformer layer.
5. Adapter tuning:  inserts adapter layers between the self-attention module
     1. $Adapter^H $: two fully connected layers with biases in an adapter layer with a nonlinearity in between
     2. $Adapter^L $: adapter layer applied only after the MLP module and after a LayerNorm
     3. $Adapter^P$
     4. $Adapter^D$

<div align=center>
<img src=https://github.com/jiayuchennlp/reading_papers/blob/main/PEFT/pictures/LoRA-2.png/>
</div>

























