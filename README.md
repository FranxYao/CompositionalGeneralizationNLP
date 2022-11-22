
# Distributional Generalization in Natural Language Processing.

Yao Fu, University of Edinburgh, yao.fu@ed.ac.uk

\*\*Update\*\*: [A Closer Look at Language Model Emergent Abilities](https://yaofu.notion.site/A-Closer-Look-at-Large-Language-Models-Emergent-Abilities-493876b55df5479d80686f68a1abd72f)

\*\*Update\*\*: [Reasoning with large language models](#reasoning-with-large-language-models)

## Introduction

Although seemingly trivial and being easily used everyday, our observation and knowledge of human language is restricted, biased and ultimately finite. 
Yet the variant of human language is at least combinatorially large, and potentially exponential or even infinite. 
How can we generalize to such large space with such limited observation? 
Are the current models capable enough to generalize on unseen linguistic scenarios? 
If one feed all possible data on the internet to a gigantic language model, can it learn everything of human language? 
If not, what is (still) missed? 
These are the problems that we would like to study through the lens of generalization. 




## Table of Content 
- [Introduction](#introduction)
- [Table of Content](#table-of-content)
- [Development of Theory](#development-of-theory)
- [Foundations](#foundations)
  - [Books](#books)
  - [Courses](#courses)
  - [Miscellaneous](#miscellaneous)
- [Classical Theory](#classical-theory)
- [Deep Learning Theory](#deep-learning-theory)
  - [Training Dynamics](#training-dynamics)
  - [Gradient Descent](#gradient-descent)
  - [Neural Tangent Kernel](#neural-tangent-kernel)
  - [Mean-Field Analysis](#mean-field-analysis)
  - [Generalization Bounds](#generalization-bounds)
- [Reasoning with Large Language Models](#reasoning-with-large-language-models)
  - [Resources](#resources)
  - [Chain of Thoughts Series](#chain-of-thoughts-series)
  - [Scratch pad](#scratch-pad)
- [Transfer Setting](#transfer-setting)
  - [Domain Adaptation & Generalization](#domain-adaptation--generalization)
  - [Compositionality](#compositionality)
  - [Invariance](#invariance)
  - [Causality](#causality)
- [Generalization in Natural Language Processing](#generalization-in-natural-language-processing)
  - [General](#general)
  - [Semantic Parsing](#semantic-parsing)
  - [Datasets](#datasets)
  - [Question Answering](#question-answering)
  - [Reading Comprehension](#reading-comprehension)
  - [Adversarial Perturbation](#adversarial-perturbation)
  - [NLP Architecture Learnability](#nlp-architecture-learnability)
- [Optimization](#optimization)
  - [Distributionally Robust Optimization](#distributionally-robust-optimization)
  - [Sharpness-aware Minimization](#sharpness-aware-minimization)
- [Practical Techniques](#practical-techniques)
  - [Architectures](#architectures)
  - [Data Augmentation](#data-augmentation)

## Development of Theory 

| Theory | Model Scale | \#Param | Data | 
| ------ | ------ | ---- | ---- | 
| Classical Supervised Learning Theory | Small model (e.g., SVMs) | <1M | i.i.d. data | 
| Deep Supervised Learning Theory | Small neural networks | < 1M | i.i.d. data | 
| Generalization in Transfer Setting | Mid neural networks | < 1G | non-i.i.d. data, structures within data, data distributional shift | 
| Compositional Generalization in NLP | Pretrained language model | < 11G | non-i.i.d. data, linguistic structures within data, domain transfer, task transfer, cross-lingual transfer | 
| Emergent Abilities in Large Language Models | Largest models so far (GPT-3, PaLM, .etc) | > 100G |  i.i.d. or non-i.i.d., Few-shot in-context learning | 


* Classical Supervised Learning Theory
  * Small model (e.g., SVMs), i.i.d. data
  * PAC, Rademancher Complexity, VC Dimension
* Deep Supervised Learning Theory 
  * Large model, neural networks, i.i.d. data
  * Over-parameterization, Regularization, Non-convex Optimization, Neural Tangent Kernel
* Generalization in Transfer Setting 
  * Large model, neural networks, non-i.i.d. data
  * Distribution Shift, Domain Adaptation, Robustness, Invariance
* Compositional Generalization in NLP 
  * Even Larger model (pretrained language model), non-i.i.d., but with intrinsic structures, data
  * Semantic Parsing, Question Answering, Language Generation
* Emergent Abilities in Large Language Models 
  * Largest models so far (GPT-3, PaLM), few-shots in-context learning, reasoning with rationales
* Practical Techniques 
  * Datasets, Data Augmentation, Architecture Design, Distributionally Robust Optimization, .etc.

----
## Foundations

### Books 

* The Syntactic Process. Mark Steedman. 2000 

* Statistical Learning Theory. Percy Liang. CS229T Notes.

* Learning Theory from First Principles. Francis Bach


### Courses

* Stanford STATS214 / CS229M: Machine Learning Theory. Tengyu Ma. 

* UIUC CS 540. [Deep Learning Theory](https://mjt.cs.illinois.edu/courses/dlt-f21/). Matus Telgarsky.

* UCLA CS269 [Foundations of Deep Learning](https://uclaml.github.io/CS269-Spring2021/)

* MIT 6.S088 [Modern Machine Learning: Simple Methods that Work](https://web.mit.edu/modernml/course/)

### Miscellaneous

* Google. [Neural Tangents](https://github.com/google/neural-tangents)

* [Off the Convex Path](http://www.offconvex.org/) blog

* [Toward theoretical understanding of deep learning](https://unsupervised.cs.princeton.edu/deeplearningtutorial.html). ICML 2018 Tutorial

* Research Vignette: Generalization and Interpolation. Daniel Hsu [[site](https://simons.berkeley.edu/news/research-vignette-generalization-and-interpolation)]


## Classical Theory

TBC


## Deep Learning Theory

* A Convergence Theory for Deep Learning via Over-Parameterization. Zeyuan Allen-Zhu, Yuanzhi Li, Zhao Song. 2019

### Training Dynamics
TBC

### Gradient Descent
TBC

### Neural Tangent Kernel

* Neural Tangent Kernel: Convergence and Generalization in Neural Networks. 
Arthur Jacot, Franck Gabriel, Cle ́ment Hongler. NeurIPS 2018

* Wide Neural Networks of Any Depth Evolve as Linear Models Under Gradient Descent. Jaehoon Lee, Lechao Xiao, Samuel S. Schoenholz, Yasaman Bahri, Roman Novak, Jascha Sohl-Dickstein, Jeffrey Pennington. NeurIPS 2019

### Mean-Field Analysis 
TBC

### Generalization Bounds
TBC

## Reasoning with Large Language Models 

### Resources 
* Stanford CS324 - Large Language Models [[link](https://stanford-cs324.github.io/winter2022/)]
* Princeton COS 597G - Understanding Large Language Models [[link](https://www.cs.princeton.edu/courses/archive/fall22/cos597G/)]
* UNC COMP790-101 - Large Language Models [[link](https://github.com/craffel/llm-seminar/)]

### Chain of Thoughts Series 

* Chain of Thought Prompting Elicits Reasoning in Large Language Models. 2022 
  * Jason Wei, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Brian Ichter, Fei Xia, Ed Chi, Quoc Le, Denny Zhou
  
* Self-Consistency Improves Chain of Thought Reasoning in Language Models. 2022
  * Xuezhi Wang, Jason Wei, Dale Schuurmans, Quoc Le, Ed Chi, Sharan Narang, Aakanksha Chowdhery, Denny Zhou

* Least-to-Most Prompting Enables Complex Reasoning in Large Language Models. 2022 
  * Denny Zhou, Nathanael Schärli, Le Hou, Jason Wei, Nathan Scales, Xuezhi Wang, Dale Schuurmans, Olivier Bousquet, Quoc Le, Ed Chi

* Selection-Inference: Exploiting Large Language Models for Interpretable Logical Reasoning. 2022 
  * Antonia Creswell, Murray Shanahan, Irina Higgins

* Rationale-Augmented Ensembles in Language Models. 2022
  * Xuezhi Wang, Jason Wei, Dale Schuurmans, Quoc Le, Ed Chi, Denny Zhou

* Minerva: Solving Quantitative Reasoning Problems with Language Models. 2022 
  * Aitor Lewkowycz, Anders Andreassen, David Dohan, Ethan Dyer, Henryk Michalewski, Vinay Ramasesh, Ambrose Slone, Cem Anil, Imanol Schlag, Theo Gutman-Solo, Yuhuai Wu, Behnam Neyshabur, Guy Gur-Ari, Vedant Misra
  
* Large Language Models are Zero-Shot Reasoners. 2022 
  * Takeshi Kojima, Shixiang Shane Gu, Machel Reid, Yutaka Matsuo, Yusuke Iwasawa

### Scratch pad 

* Notes on Teaching GPT-3 Adding Numbers. 2022 [[link](https://lingo.csail.mit.edu/blog/arithmetic_gpt3/)]
  * Ekin Akyürek and Afra Feyza Akyürek 

* Show Your Work: Scratchpads for Intermediate Computation with Language Models. 2022
  * Maxwell Nye, Anders Johan Andreassen, Guy Gur-Ari, Henryk Michalewski, Jacob Austin, David Bieber, David Dohan, Aitor Lewkowycz, Maarten Bosma, David Luan, Charles Sutton, Augustus Odena


## Transfer Setting 

* Distributional Generalization: A New Kind of Generalization. Preetum Nakkiran and Yamini Bansal

### Domain Adaptation & Generalization 

* A Theory of Learning from Different Domains. Shai Ben-David John Blitzer Koby Crammer Alex Kulesza Fernando Pereira Jennifer Vaughan. Machine Learning 2010

* Domain-Adversarial Training of Neural Networks. Yaroslav Ganin, Evgeniya Ustinova, Hana Ajakan, Pascal Germain, Hugo Larochelle, François Laviolette, Mario Marchand, Victor Lempitsky. JMLR 2016

* Adversarial Multiple Source Domain Adaptation. Han Zhao, Shanghang Zhang, Guanhang Wu, José MF Moura, Joao P Costeira, Geoffrey J Gordon. NeurIPS 2018

* In Search of Lost Domain Generalization. Ishaan Gulrajani, David Lopez-Paz. 2020

### Compositionality 

* Measuring Compositionality in Representation Learning. Jacob Andres. ICLR 2019 

* Systematic Generalization: What Is Required and Can It Be Learned? Dzmitry Bahdanau\*, Shikhar Murty\*, Michael Noukhovitch, Thien Huu Nguyen, Harm de Vries, Aaron Courville. ICLR 2019

* Beyond I.I.D.: Three Levels of Generalization for Question Answering on Knowledge Bases. Yu Gu, Sue Kase, Michelle Vanni, Brian Sadler, Percy Liang, Xifeng Yan, Yu Su. WWW 2021


### Invariance 

* Invariant Risk Minimization. Martin Arjovsky, Léon Bottou, Ishaan Gulrajani, David Lopez-Paz. 

* The Risks of Invariant Risk Minimization. Elan Rosenfeld, Pradeep Kumar Ravikumar, Andrej Risteski. ICLR 2020 

* Does Invariant Risk Minimization Capture Invariance? Pritish Kamath, Akilesh Tangella, Danica J. Sutherland, Nathan Srebro. AISTATS 2021 

* Iterative Feature Matching: Toward Provable Domain Generalization with Logarithmic Environments. Yining Chen, Elan Rosenfeld, Mark Sellke, Tengyu Ma, Andrej Risteski.


### Causality
* Towards Causal Representation Learning. Bernhard Schölkopf, Francesco Locatello, Stefan Bauer, Nan Rosemary Ke, Nal Kalchbrenner, Anirudh Goyal, Yoshua Bengio

* A Meta-Transfer Objective for Learning to Disentangle Causal Mechanisms. Yoshua Bengio, Tristan Deleu, Nasim Rahaman, Rosemary Ke, Sébastien Lachapelle, Olexa Bilaniuk, Anirudh Goyal, Christopher Pal

* Causal Inference using Invariant Prediction: Identification and Confidence Intervals. Jonas Peters, Peter Bühlmann, Nicolai Meinshausen

* Anchor regression: heterogeneous data meet causality. Dominik Rothenhäusler, Nicolai Meinshausen, Peter Bühlmann, Jonas Peters


## Generalization in Natural Language Processing

### General 

* Evaluating Models’ Local Decision Boundaries via Contrast Sets. Matt Gardner and others, EMNLP Findings 2020. 


### Semantic Parsing 

* Coarse-to-Fine Decoding for Neural Semantic Parsing. Li Dong and Mirella Lapata. 2018 

* Language to Logical Form with Neural Attention. Li Dong and Mirella Lapata. 2016 

* Learning a Neural Semantic Parser from User Feedback. Srinivasan Iyer, Ioannis Konstas, Alvin Cheung, Jayant Krishnamurthy, Luke Zettlemoyer. ACL 2017 

* Generalization without systematicity: On the compositional skills of sequence-to-sequence recurrent networks. Brenden M. Lake, Marco Baroni. ICML 2018

* Improving Text-to-SQL Evaluation Methodology. Catherine Finegan-Dollak, Jonathan K. Kummerfeld, Li Zhang, Karthik Ramanathan, Sesh Sadasivam, Rui Zhang, Dragomir R. Radev

* Compositional Generalization for Neural Semantic Parsing via Span-level Supervised Attention. Pengcheng Yin, Hao Fang, Graham Neubig, Adam Pauls, Emmanouil Antonios Platanios, Yu Su, Sam Thomson, Jacob Andreas. NAACL 2021 

* Compositional generalization through meta sequence-to-sequence learning. Brenden M. Lake. NeurIPS 2019

* Lexicon Learning for Few-Shot Neural Sequence Modeling. Ekin Akyürek, Jacob Andreas

* Sequence-to-Sequence Learning with Latent Neural Grammars. Yoon Kim


### Datasets

* Measuring Compositional Generation: A Comprehensive Method on Realistic Data. Daniel Keysers, Nathanael Schärli, Nathan Scales, Hylke Buisman, Daniel Furrer, Sergii Kashubin, Nikola Momchev, Danila Sinopalnikov, Lukasz Stafiniak, Tibor Tihon, Dmitry Tsarkov, Xiao Wang, Marc van Zee, Olivier Bousquet. ICLR 2020

* COGS: A Compositional Generalization Challenge Based on Semantic Interpretation. Najoung Kim, Tal Linzen. EMNLP 2020



### Question Answering

* Question and Answer Test-Train Overlap in Open-Domain Question Answering Datasets. Patrick Lewis, Pontus Stenetorp, Sebastian Riedel. EACL 2020 

* Learning to Compose Neural Networks for Question Answering. Jacob Andreas, Marcus Rohrbach, Trevor Darrell, Dan Klein. NAACL 2016

### Reading Comprehension 

TBC 

### Adversarial Perturbation

TBC


### NLP Architecture Learnability

* Memory-Augmented Recurrent Neural Networks Can Learn Generalized Dyck Languages. Mirac Suzgun, Sebastian Gehrmann, Yonatan Belinkov, Stuart M. Shieber.

* RNNs can generate bounded hierarchical languages with optimal memory. John Hewitt, Michael Hahn, Surya Ganguli, Percy Liang, Christopher D. Manning. EMNLP 2020

* A Formal Hierarchy of RNN Architectures. William Merrill, Gail Weiss, Yoav Goldberg, Roy Schwartz, Noah A. Smith, Eran Yahav. ACL 2020 

* Theoretical Limitations of Self-Attention in Neural Sequence Models. Michael Hahn. TACL 2019

* On the Ability and Limitations of Transformers to Recognize Formal Languages. Satwik Bhattamishra, Kabir Ahuja, Navin Goyal. EMNLP 2020

## Optimization

### Distributionally Robust Optimization

* Robust Solutions of Optimization Problems Affected by Uncertain Probabilities. Aharon Ben-Tal, Dick den Hertog, Anja De Waegenaere, Bertrand Melenberg, Gijs Rennen. Management Science 2013

* Certifying Some Distributional Robustness with Principled Adversarial Training. Aman Sinha, Hongseok Namkoong, Riccardo Volpi, John Duchi. ICLR 2018

* Does Distributionally Robust Supervised Learning Give Robust Classifiers? Weihua Hu, Gang Niu, Issei Sato, Masashi Sugiyama. ICML 2018 

* Distributionally Robust Neural Networks for Group Shifts: On the Importance of Regularization for Worst-Case Generalization. Shiori Sagawa, Pang Wei Koh, Tatsunori B. Hashimoto, Percy Liang. ICLR 2020

* Distributionally Robust Language Modeling. Yonatan Oren, Shiori Sagawa, Tatsunori B. Hashimoto, Percy Liang. EMNLP 2019
 
* Modeling the Second Player in Distributionally Robust Optimization. Paul Michel, Tatsunori Hashimoto, Graham Neubig. ICLR 2021

### Sharpness-aware Minimization
TBC 



## Practical Techniques

### Architectures 

* Dynamic Inference with Neural Interpreters. Muhammad Waleed Gondal, Nasim Rahaman, Shruti Joshi, Peter Gehler, Yoshua Bengio†, Francesco Locatello†, Bernhard Schölkopf. NeurIPS 2021

* Compositional Generalization via Neural-Symbolic Stack Machines. Xinyun Chen, Chen Liang, Adams Wei Yu, Dawn Song, Denny Zhou. NeurIPS 2020 

* Learning Compositional Rules via Neural Program Synthesis. Maxwell I. Nye, Armando Solar-Lezama, Joshua B. Tenenbaum, Brenden M. Lake. NeurIPS 2020 

* Compositional Generalization by Learning Analytical Expressions. Qian Liu, Shengnan An, Jian-Guang Lou, Bei Chen, Zeqi Lin, Yan Gao, Bin Zhou, Nanning Zheng, Dongmei Zhang. NeurIPS 2020 

* Towards Complex Programs from Input-Output Examples. Xinyun Chen Chang Liu Dawn Song. ICLR 2018.


### Data Augmentation 
* Good-Enough Compositional Data Augmentation. Jacob Andreas. ACL 2020 

* Sequence-Level Mixed Sample Data Augmentation. Demi Guo, Y. Kim, Alexander M. Rush. EMNLP 2020. 

* Learning to Recombine and Resample Data for Compositional Generalization. Ekin Akyürek, Afra Feyza Akyurek, Jacob Andreas. ICLR 2021 

* Substructure Substitution: Structured Data Augmentation for NLP. Haoyue Shi, Karen Livescu, Kevin Gimpel. 2021 

* Improving Text-to-SQL Evaluation Methodology. Catherine Finegan-Dollak, Jonathan K. Kummerfeld, Li Zhang, Karthik Ramanathan, Sesh Sadasivam, Rui Zhang, Dragomir Radev. ACL 2018 



