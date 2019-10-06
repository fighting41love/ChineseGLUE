# ChineseGLUE
Language Understanding Evaluation benchmark for Chinese: datasets, baselines, corpus and leaderboard

中文语言理解测评基准，包括代表性的数据集、基准(预训练)模型、语料库、排行榜。  

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

   A huge amount of raw corpus for pre-train or language modeling research purpose. It will contains around 10G raw corpus in 2019; 
   
   In the first half year of 2020, it will include at least 30G raw corpus; By the end of 2020, we will include enough
   
   raw corpus, such as 100G, so big enough that you will need no more raw corpus for general purpose language modeling.

   You can use it for general purpose or domain adaption, or even for text generating. when you use for domain adaption, 
   you will able to select corpus you are interested in.

数据集介绍与下载
--------------------------------------------------------------------
##### 1. LCQMC 口语化描述的语义相似度任务
输入是两个句子，输出是0或1。其中0代表语义不相似，1代表语义相似。

        数据量：训练集(238,766)，验证集(8,802)，测试集(12,500)
        例子： 
         1.聊天室都有哪些好的 [分隔符] 聊天室哪个好 [分隔符] 1
         2.飞行员没钱买房怎么办？ [分隔符] 父母没钱买房子 [分隔符] 0

##### 2. XNLI 语言推断任务
跨语言理解的数据集，给定一个前提和假设，判断这个假设与前提是否具有蕴涵、对立、中性关系。
                
        数据量：训练集(392,703)，验证集(？)，测试集(？)
        例子： 
         1.从 概念 上 看 , 奶油 收入 有 两 个 基本 方面 产品 和 地理 .[分隔符] 产品 和 地理 是 什么 使 奶油 抹 霜 工作 . [分隔符]	neutral
         2.我们 的 一个 号码 会 非常 详细 地 执行 你 的 指示 [分隔符] 我 团队 的 一个 成员 将 非常 精确 地 执行 你 的 命令	[分隔符] entailment
        
        原始的XNLI覆盖15种语言（含低资源语言）。我们选取其中的中文，并将做格式转换，使得非常容易进入训练和测试阶段。


##### 3.TNEWS 今日头条中文新闻（短文本）分类
        
        数据量：训练集(266,000)，验证集(57,000)，测试集(57,000)
        例子：
        6552431613437805063_!_102_!_news_entertainment_!_谢娜为李浩菲澄清网络谣言，之后她的两个行为给自己加分_!_佟丽娅,网络谣言,快乐大本营,李浩菲,谢娜,观众们
        每行为一条数据，以_!_分割的个字段，从前往后分别是 新闻ID，分类code，分类名称，新闻字符串（仅含标题），新闻关键词

##### 4. 更多数据集添加中，Comming soon!

更多数据集添加中，目标是8个覆盖不同任务的有代表性的数据集；如果你有定义良好的数据集，请与我们取得联系。

##### 数据集下载 <a href="https://storage.googleapis.com/chineseglue/chineseGLUEdatasets.v0.0.1.zip">整体下载</a>

或使用命令：

    wget https://storage.googleapis.com/chineseglue/chineseGLUEdatasets.v0.0.1.zip

基准测评-排行榜
---------------------------------------------------------------------
TODO
此处将会被指向到一个排行榜的网站地址

语料库：语言建模、预训练或生成型任务
---------------------------------------------------------------------
可用于语言建模、预训练或生成型任务等，数据量超过10G，主要部分来自于<a href="https://github.com/brightmart/nlp_chinese_corpus">nlp_chinese_corpus项目</a>

当前语料库按照【预训练格式】处理，内含有多个文件夹；每个文件夹有许多不超过4M大小的小文件，文件格式符合预训练格式：每句话一行，文档间空行隔开。

包含如下子语料库（总共14G语料）：

1、新闻语料: 8G语料，分成两个上下两部分，总共有2000个小文件。

2、社区互动语料：3G语料，包含3G文本，总共有900多个小文件。

3、维基百科：1.1G左右文本，包含300左右小文件。

4、评论数据：2.3G左右文本，含有811个小文件，合并<a href="https://github.com/InsaneLife/ChineseNLPCorpus">ChineseNLPCorpus</a>的多个评论数据，清洗、格式转换、拆分成小文件。

这些语料，你可以通过上面这两个项目，清洗数据并做格式转换获得；

你也可以通过邮件申请（chineseGLUE#163.com）获得单个项目的语料，告知单位或学校、姓名、语料用途；

如需获得ChineseGLUE项目下的所有语料，需成为ChineseGLUE组织成员，并完成一个（小）任务。

成为ChineseGLUE组织的创始成员
---------------------------------------------------------------------
##### 你将可以：

1、成功中国第一个中文任务基准测评的创始会员

2、能与其他专业人士共同贡献力量，促进中文自然语言处理事业的发展

3、参与部分工作后，获得已经清洗并预训练的后的、与英文wiki & bookCorpus同等量级、大规模的预训练语料，用于研究目的。

4、优先使用state of the art的中文预训练模型，包括各种体验版或未公开版本

##### 如何参与：

发送邮件 chineseGLUE#163.com，简要介绍你自己、背景、工作或研究方向、你的组织、在哪方面可以为社区贡献力量，我们评估后会与你取得联系你。

任务清单
---------------------------------------------------------------------
1、成功推荐或贡献数据集，数据集需有代表性，一般为分类或句子对任务，阅读理解任务可以简化过来（如线索与问题或答案），数据应拆分成训练、验证和测试集。

2、编写特定任务模型的训练、预测的方法(TensorFlow, PyTorch, Keras)；

3、对当前主流模型（如bert/bert_wwm_ext/roberta/albert/ernie/ernie2.0等），结合ChineseGLUE的数据集，做准确率测试。

4、排行榜landing页

5、介绍中文语言理解测评基准(ChineseGLUE)

6、测评系统主要功能开发

Timeline 时间计划:
---------------------------------------------------------------------
2019-10-20 to 2019-12-31: beta version of ChineseGLUE

2020.1.1 to 2020-12-31: official version of ChineseGLUE

2021.1.1 to 2021-12-31: super version of ChineseGLUE

Contribution 贡献你的力量，从今天开始
---------------------------------------------------------------------

Share your data set with community or make a contribution today! Just send email to chineseGLUE#163.com, 

or join QQ group: 836811304

Reference:
---------------------------------------------------------------------
1、<a href="https://openreview.net/pdf?id=rJ4km2R5t7">GLUE: A Multi-Task Benchmark and Analysis Platform for Natural Language Understanding</a>

2、<a href="https://w4ngatang.github.io/static/papers/superglue.pdf">SuperGLUE: A Stickier Benchmark for General-Purpose Language Understanding Systems</a>

3、<a href="https://www.aclweb.org/anthology/C18-1166.pdf">LCQMC: A Large-scale Chinese Question Matching Corpus</a>

4、<a href="https://arxiv.org/pdf/1809.05053.pdf">XNLI: Evaluating Cross-lingual Sentence Representations</a>

5、<a href="https://github.com/fate233/toutiao-text-classfication-dataset">TNES: toutiao-text-classfication-dataset</a>

6、<a href="https://github.com/brightmart/nlp_chinese_corpus">nlp_chinese_corpus: 大规模中文自然语言处理语料 Large Scale Chinese Corpus for NLP</>

7、<a href="https://github.com/InsaneLife/ChineseNLPCorpus">ChineseNLPCorpus</>
