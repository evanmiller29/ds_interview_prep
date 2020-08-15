---
type: slides
---

# Decision Trees

Notes: Text at the end of a slide prefixed like this will be displayed as
speaker notes on the side. Slides can be separated with a divider: ---.

--- 

# Decision Tree - Asumptions

[See here for more information](https://towardsdatascience.com/decision-tree-algorithm-explained-83beb6e78ef4)

- In the beginning, the whole training set is considered as the root.
- Feature values are preffered to be categorical. If they are continuous then they are discretized before building the model.
- Records are distributed recursively on the basis of attribute values.
- Order to placing attributes as root or internal node of the tree is done by using some statistical approach.

---

# Decision Tree Pseudocode (ID3)

1. Begins with the original set S as the root node
2. On each iteration of the algorithm, it iterates through the very unused attribte of the set S and calculates Entropy(H) and Information Gain (IG) of this attribute
3. It then selects the attribute which as the smallest Entropy or largest Information Gain
4. The dataset is then split by the selected attribute to produce a subset of the data.
5. The algorithm continues on each subset, only considering attributes not used before. 

---

# Entropy

Entropy is a measure of randomness in the information being processed. 

The higher the entropy, the harder it is to draw any conclusions from that information. 
For example: flipping a coin.

- ID3 decision trees: A branch wth an entropy of zero is a leaf node and a branch with non zero entropy needs further splitting.

---

Information Gain

Information Gain is a statistical property that measures how well a given attribute separates the training examples according to their target classification.
Constructing a decision tree is all about finding an attribute that returns the highest information gain or lowest entropy.

---

# How to avoid overfitting in DTs

Sometimes DTs will fit so intensely that they will have 1 leaf for every observation, getting 100% on the training set (really high variance).

There are two ways of removing overfitting from DTS:

1. Pruning Decision Trees.
2. Random Forest.

---

# Pruning Decision Trees

You cut the branches off the tree.

You split the dataset into training and validation and if a branch doesn't cause a drop in validation accuracy then it gets the cut. 
You generally need to consider a few branch combinations to make sure that your branch really has no importance on validation accuracy though.

--- Random Forest

Random forests are called this because you fit many DTs on random subsets of columns and rows and use voting / averaging to determine the prediction from all.
This reduces the variance of the DTs massively. 

---
