# predict-gene-expression-using-graph-word2vec
This repository presents an example of prediction of protein expression. using a graph and known levels of expression on training set (80% of nodes).

From Wikipedia (https://en.wikipedia.org/wiki/Gene_expression)
Gene expression is the most fundamental level at which the genotype gives rise to the phenotype, i.e. observable trait.

<b>About the dataset.</b>
The dataset is a graph of interactions between proteins. The nodes represent pairs gene-protein (it is considered that both concepts play the same role in our setting) and the edges represent interaction between proteins.

Specifically, the graph is given by the list of its edges (`edges`). The data about target variable (gene expression) is subdivided into `train` и `test` sets.

The dataset has been simplified to meet the following conditions
* the graph is connected (tested in the notebook); 
* most important hubs are removed;
* the graph density is reduced;
* the problem can be solved by classical ML approaches.


<b>About the problem.</b>
The model accuracy is evaluated using its MSE on the test set.

<b>Conclusions.</b>
The best error on test set is of order of 0.2, which is less than one third of the mean of the target variable.

The results show some random behavior due to the embedding 'word2vec', see:

https://github.com/piskvorky/gensim/wiki/Recipes-&-FAQ#q11-ive-trained-my-word2vecdoc2vecetc-model-repeatedly-using-the-exact-same-text-corpus-but-the-vectors-are-different-each-time-is-there-a-bug-or-have-i-made-a-mistake-2vec-training-non-determinism
" So, it is to be expected that models vary from run to run, even trained on the same data."


The optimal embedding size seems to be 30. Indeed, the error on test set remains stable or increases afterwards.
The error on test set is at least 4 times the error on training set. This property of the model seems inherent and independent of the the embedding size.

<b>Feedback and additional questions.</b>
All questions about the dataset or the problem should be adressed to Alexander Milenkin:
* Telegram: Alerin75infskin
* Email: milenkin.aa@phystech.edu

All questions about the source code should be adressed to its author Alexandre Aksenov:
* GitHub: Alexandre-aksenov
* Email: alexander1aksenov@gmail.com

