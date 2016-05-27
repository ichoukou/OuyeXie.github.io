# Introduction

 - [Expectation Maximization Clustering](http://docs.rapidminer.com/studio/operators/modeling/segmentation/expectation_maximization_clustering.html)
    - Expectation Maximization algorithmThe basic approach and logic of this clustering method is as follows. Suppose you measure a single continuous variable in a large sample of observations. Further, suppose that the sample consists of two clusters of observations with different means (and perhaps different standard deviations); within each sample, the distribution of values for the continuous variable follows the normal distribution. The goal of EM clustering is to estimate the means and standard deviations for each cluster so as to maximize the likelihood of the observed data (distribution). Put another way, the EM algorithm attempts to approximate the observed distributions of values based on mixtures of different distributions in different clusters. The results of EM clustering are different from those computed by k-means clustering. The latter will assign observations to clusters to maximize the distances between clusters. The EM algorithm does not compute actual assignments of observations to clusters, but classification probabilities. In other words, each observation belongs to each cluster with a certain probability. Of course, as a final result you can usually review an actual assignment of observations to clusters, based on the (largest) classification probability.

# Weka explaination 

NAME
weka.clusterers.EM

SYNOPSIS
Simple EM (expectation maximisation) class.

EM assigns a probability distribution to each instance which indicates the probability of it belonging to each of the clusters. EM can decide how many clusters to create by cross validation, or you may specify apriori how many clusters to generate.

The cross validation performed to determine the number of clusters is done in the following steps:
1. the number of clusters is set to 1
2. the training set is split randomly into 10 folds.
3. EM is performed 10 times using the 10 folds the usual CV way.
4. the loglikelihood is averaged over all 10 results.
5. if loglikelihood has increased the number of clusters is increased by 1 and the program continues at step 2. 

The number of folds is fixed to 10, as long as the number of instances in the training set is not smaller 10. If this is the case the number of folds is set equal to the number of instances.

Missing values are globally replaced with ReplaceMissingValues.

OPTIONS
seed -- The random number seed to be used.

numFolds -- The number of folds to use when cross-validating to find the best number of clusters (default = 10)

numExecutionSlots -- The number of execution slots (threads) to use. Set equal to the number of available cpu/cores

debug -- If set to true, clusterer may output additional info to the console.

numKMeansRuns -- The number of runs of k-means to perform.

displayModelInOldFormat -- Use old format for model output. The old format is better when there are many clusters. The new format is better when there are fewer clusters and many attributes.

minLogLikelihoodImprovementIterating -- The minimum improvement in log likelihood required to perform another iteration of the E and M steps

minLogLikelihoodImprovementCV -- The minimum improvement in cross-validated log likelihood required in order to consider increasing the number of clusters when cross-validiting to find the best number of clusters

maximumNumberOfClusters -- The maximum number of clusters to consider during cross-validation to select the best number of clusters

numClusters -- set number of clusters. -1 to select number of clusters automatically by cross validation.

doNotCheckCapabilities -- If set, clusterer capabilities are not checked before clusterer is built (Use with caution to reduce runtime).

maxIterations -- maximum number of iterations

minStdDev -- set minimum allowable standard deviation

