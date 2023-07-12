# 思维链综述
## 早期工作： 
- 动机：传统的prompt对需要进行复杂推理的任务效果不佳，如数学题、常识、符号推理等。
- 提出：分解任务，一步步推理得到最终答案
- 相关工作：
  - **zero-shot cot** : Large Language Models are Zero-Shot Reasoners [paper](https://arxiv.org/abs/2205.11916)
    1.  Let's think step by step
  - **few-shot cot** : Chain-of-thought prompting elicits reasoning in large language models [paper](https://arxiv.org/abs/2201.11903)
    1.  从训练集中选择8个有代表性的例子
    2.  为8个例子分别写出CoT过程，采用 few-shot 方法进行预测
  - 不足
    1.  人工构造cot，不够灵活
    2.  采用greedy解码方式，只能得到一个cot过程及结果，而实际上复杂任务可能存在多种分解过程及结果
    3.  需要基于base model要大于100B才有效果
    4.  采用链条（chain）的形式分解步骤，从左到右（left-to-right）生成结果，难以适应更加复杂的任务
