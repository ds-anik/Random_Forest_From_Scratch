## What are Random forests? 

<div align="justify">Random forests (RF) are basically a bag containing  <b>n</b>  Decision Trees (DT) having a different set of hyper-parameters and trained on different subsets of data. Let’s say we have 100 decision trees in our Random forest bag!! These decision trees have a different set of hyper-parameters and a different subset of training data, so the decision or the prediction given by these trees can vary a lot. Let’s consider that we somehow trained all these 100 trees with their respective subset of data. Now We want to calculate all the hundred trees  predictions on the test data. we need to take only  one example or one test data, we do it by taking a simple vote. We go with what the majority of the trees have predicted for that example.</div>


<img align="center" alt="GIF" src="https://github.com/ds-anik/Random_Forest_From_Scratch/blob/main/data/RF.gif" />

<div align="justify">In the above illustration, we can see how an example is classified using n trees where the final prediction is done by taking a vote from all n trees. The fundamental concept behind random forest is a simple but powerful one — <b>the wisdom of crowds</b>. In data science speak, the reason that the random forest model works so well is:</div>
<br>
<div align="justify"><b>A large number of relatively uncorrelated models (trees) operating as a committee will outperform any of the individual constituent models.</b></div>
<br>
<div align="justify">The random forest is a algorithm uses <b>bagging</b> and <b>>feature randomness</b> when building each individual tree to try to create an uncorrelated forest of trees whose prediction by committee is more accurate than that of any individual tree.</div>

What do we need in order for our random forest to make accurate class predictions?
- We need features that have at least some predictive power. After all, if we put garbage in then we will get garbage out.
- <div align="justify">The trees of the forest and more importantly their predictions need to be uncorrelated (or at least have low correlations with each other). While the algorithm itself via feature randomness tries to engineer these low correlations for us, the features we select and the hyper-parameters we choose will impact the ultimate correlations as well.</div>

### Dataset Description:

The housing price prediction dataset is taken from an ongoing [Kaggle competition](https://www.kaggle.com/c/house-prices-advanced-regression-techniques).
The goal is predict the price of a house given its 79 different attributes So it is a regression problem. Therefore Our implemented random forest should be able to predict a value (housing price) rather than a classifying a class.