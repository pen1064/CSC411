Using this as excuse to build adaboost from semi-scratch (at least the decision tree is taken from sklearn). \
In Adaboost, the weight of the incorrectly labelled sample will be increased to build the next tree. 
Here are the key steps:\
1. Fit tree to the data
2. Evaluate the fit tree (depth = 1)
3. Calcuate the error (whatever that's incorrectly classified) 
4. Use the erorr to calculate the alpha (a.k.a amount of say), a float number that is "inversely" proportional to the error
5. Now time to increase the weight for the incorrectly classified sample with alpha 
6. Repeat the tree planting process until you finish planting the targeted number of trees in your "garden" 
NOTE: The size of your tree depends on how well it predicts (amount of say)
For example: 
Predicted Value = alpha1*Tree_1 + alpha2*Tree_2 + ..... + alphan*Tree_n

One key difference in Adaboost wrt XGBoost:
1. In XGBoost, you deal with pesuedo residual. 
2. The tree building process is based on similarity score, then you calculate the Gain to see if you want that or not (if Gain less than the node, don bother)
3. The tree depth can be greater than 1 (given that you can prune the tree even when gamma = 0)
4. The tree is proportional to the learning rate 
