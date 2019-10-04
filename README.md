# ChineseGLUE
Language Understanding Evaluation benchmark for Chinese: datasets, baselines, corpus and leaderboard

中文语言理解测评基准，包括代表性的数据集、基准模型、语料库、排行榜。  

我们会选择一系列有一定代表性的任务对应的数据集，做为我们测试基准的数据集。这些数据集会覆盖不同的任务、数据量、任务难度。

ChineseGLUE的定位
---------------------------------------------------------------------
为更好的服务中文语言理解、任务和产业界，做为通用语音模型测评的补充，通过完善中文语言理解基础设施的方式来促进中文语言模型的发展

Why do we need a benchmark for Chinese lanague understand evaluation?

为什么我们需要一个中文任务的基准测试？ 
---------------------------------------------------------------------
首先，中文是一个大语种，有其自身的特定、大量的应用。

    如中文使用人数近14亿，是联合国官方语言之一，产业界有大量的的朋友在做中文的任务。
    中文是象形文字，有文字图形；字与字之间没有分隔符，不同的分词(分字或词)会影响下游任务。

其次，相对于英文的数据集，中文的公开可用的数据集还比较少。
     
     很多数据集是非公开的或缺失基准测评的；多数的论文描述的模型是在英文数据集上做的测试和评估，那么对于中文效果如何？不得而知。

再次，语言理解发展到当前阶段，预训练模型极大的促进了自然语言理解。

     不同的预训练模型相继产生，但不少最先进(state of the art)的模型，并没有官方的中文的版本，也没有对这些预训练模型在不同任务上的公开测试，
     导致技术的发展和应用还有不少距离，或者说技术应用上的滞后。

那么，如果有一个中文任务的基准测试，包含一批大众能广泛使用和测评的数据集、适用中文任务的特点、能紧跟当前世界技术的发展，
     
     能缓解当前中文任务的一些问题，并促进相关应用的发展。

中文任务的基准测试-内容体系 Contents
--------------------------------------------------------------------
Language Understanding Evaluation benchmark for Chinese(ChineseGLUE) got ideas from GLUE, which is a collection of 

resources for training, evaluating, and analyzing natural language understanding systems. SuperGLUE consists of: 

##### 1）中文任务的基准测试，覆盖多个不同程度的语言任务 
  
  A benchmark of several sentence or sentence pair language understanding tasks. 

 Currently the datasets used in these tasks are come from public. We will include datasets with private test set before
 
 the end of 2019.

##### 2）公开的排行榜 
  
  A public leaderboard for tracking performance. You will able to submit your prediction files on these tasks,

each task will be evaluated and scored, a final score will also be available.

##### 3）基线模型，包含开始的代码、预训练模型 
  
  baselines for ChineseGLUE tasks. baselines will be available in TensorFlow,PyTorch,Keras and PaddlePaddle.

##### 4）语料库，用于语言建模、预训练或生成型任务 

   A huge amount of raw corpus for pre-train or language modeling. It will contains more than 10G corpus. 

   You can use it for general purpose or domain adaption, or even for text generating. when you use for domain adaption, 
   you will able to select corpus you are interested in.

Timeline 时间计划:
---------------------------------------------------------------------
2019-10-20 to 2019-12-31: beta version of ChineseGLUE

2020.1.1 to 2020-12-31: official version of ChineseGLUE

2021.1.1 to 2021-12-31: super version of ChineseGLUE

Contribution 贡献你的力量，从今天开始
---------------------------------------------------------------------

Share your data set with community or make a contribution today! Just send email to brightmart@otmail.com, or join QQ group: 836811304

Reference:
---------------------------------------------------------------------
1、<a href="https://openreview.net/pdf?id=rJ4km2R5t7">GLUE: A Multi-Task Benchmark and Analysis Platform for Natural Language Understanding</a>

2、<a href="https://w4ngatang.github.io/static/papers/superglue.pdf">SuperGLUE: A Stickier Benchmark for General-Purpose Language Understanding Systems</a>