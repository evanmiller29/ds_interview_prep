---
type: slides
---

# Gradient Boosting Machines

Notes: Text at the end of a slide prefixed like this will be displayed as
speaker notes on the side. Slides can be separated with a divider: ---.

--- 

# What is it?

It's theoretically very similar to Adaboost. It's just a way of making weak learners more accurate than the sum of their whole.
The idea is that you ignore the cases where the weak can easily predict, and focus on the tougher observations. 

--- 

# How Gradient Boosting works

1. A loss function to be optimized.
2. A weak learner to make predictions.
3. An additive model to add  weak learners to mimize the loss function.

---

# 1. A loss function to be optimized

The loss function used depends on the type of problem being solved. 

It needs to be differentiable, and most of the major metrics are supported.

---

# 2. Weak Learner

DTs are used as the weak learner for GBMs. 

Specifically regression trees are used that output real values for splits and whose output can be added together, allowing subsequent models to be added and "correct" the residuals in the predictions.

Trees are constructed in a greedy manner, choosing the best split points based on purity scores like Gini.

It is common to restrict the weak learners in specific ways such as limiting:

- Layers
- Nodes
- Splits
- Leaf nodes

This is to ensure that the learners remain weak, but can still be constructed in a greedy manner. 

---

# 3. Additive Model

Trees are added one at a time and existing trees are not changed. 

A gradient descent procedure is used to mimimize the loss when adding trees. Traditionally gradient descent is used to mimimize a set of params, but in this case we're looking at weak learner submodels.

After calculating the loss, to perform the gradient descent procedure, we must add a tree to the model that reduces the loss. 
We do this by parameterizing a tree and moving in the right direction (reducing loss function).

The output of this tree is then used in an effort to improve the final output of the model.

Training stops when a fixed number of trees is grown or until accuracy doesn't improve on an external validation dataset.

---

# How to improve a GBM

GBM are greedy and can easily overfit a dataset. So can stop this by:

1. Tree contstraints
	+ Number of trees: generally adding more trees to a GBM can be very slow to overfit. Keep adding until no improvement
	+ Tree depth: Deeper trees are more complex, so shorter trees preferred. 4-8 levels.
	+ Number of nodes/leaves: Can constrain the size of the trees, but not constrained to symetrical structure if other constraints are used. 
	+ Number of observations per split
	+ Minumum improvement to loss
2. Shrinkage
3. Random sampling
4. Penalized learning (learning rate, early stoppping)

---

# Links

- https://machinelearningmastery.com/gentle-introduction-gradient-boosting-algorithm-machine-learning/

---
