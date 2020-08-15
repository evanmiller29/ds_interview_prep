---
type: slides
---

# Random Forests

Notes: Text at the end of a slide prefixed like this will be displayed as
speaker notes on the side. Slides can be separated with a divider: ---.

--- 

# Ensemble Methods

- Sequential ensemble methods
	+ Where base learners are generated sequentially (Adaboost, GBM?). 
	+ The basic motivation of sequential methods is to exploit the dependence between the base learners
	+ Overall performance can be boosted by weighting previously mislabelled examples with higher weights.
- Paralell ensemble methods
	+ Where base learners are generated in parallel (Random Forests).
	+ The basic motivation of parallel methods is to exploit independence between the base learners since the error can be reduced drastically by averaging.

---

# Random Forest - key things

- Low correlation between base learners is important otherwise the same mistakes will be made.
- Bagging is used (randomly sampling rows and columns with replacement) to create a large number of diverse DTs
- Features DO NOT need to be scaled. Discretizing already takes care of this.

---

# Random Forest - Psuedocode

1. Randomly select "k" features from total features.
2. Among the "k" features calculate the node "d" using the best split point.
3. Split based on where you get the lowest entropy or highest information gain
4. Keep splitting until you reach "l" number of splits
5. Repeat 1-4 for until "n" to create "n" DTs
