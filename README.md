# AIstudio_66
ULMFiT，一种可以应用NLP中任何任务的迁移学习方法。在6个文本分类的任务上显着优于当前最好模型，并再大多数数据集上减少18-24％的错误率。
LMFiT 方法分为以下几个阶段：
LM pre-training：此阶段借鉴 CV 中的 ImageNet，在通用领域语料库（文中用的是Wikitext-103，其包含 28,595 篇维基百科文章和 1030 亿个单词）上训练语言模型（文中用的是 merity 等人提出的 AWD-LSTM），从而捕获不同层次文本的一般特征。
LM fine-tuning：此阶段的目标是针对 target domain 上微调 Language Model。在这个阶段，作者用了 Discriminative fine-tuning 和 Slanted triangular learning rates 两个 tricks，以学习不同层次文本在 target domain 上的特征。
Classifier fine-tuning：此阶段主要是训练模型的顶层结构。在这个阶段，作者用了 Concat pooling，Gradual unfreezing，BPTT for Text Classification (BPT3C) 和 Bidirectional language model 四个 tricks。
