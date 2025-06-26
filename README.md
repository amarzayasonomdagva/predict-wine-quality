# predict-wine-quality

Instruction:

You have been given a data set of thousands of wines produced in a particular region of Europe. The data contain physiochemical information about the wines, such as their pH and their total sulfur dioxide content. Each wine in the data also contains a ‘quality’ rating—the target outcome variable—denoting the wine’s overall quality. A new batch of exactly 500 wines has just been produced, but no one has had a chance to taste them yet. You must use kNN, LDA, or a tree-based algorithm discussed in class to assist you in choosing your 20 wines for purchase.

# My approach:

I explored relationships between the three variables I chose, split wine scores into three categories defining their quality, and built kNN, LDA, and Tree.

## kNN:

The overall accuracy is relatively high at nearly 73% for k=13. However, I noticed that as k increases, although accuracy improves, the model struggles to correctly identify "Worst" wines, with only 5 correctly classified at k=13. This demonstrates that KNN is not effective for predicting the lowest-quality wines. This is because the majority of the initial data is classified as "okay" and is affecting the ability of the model to predict "worst" wine due to their significantly smaller representation in the dataset. On the other hand, it is better at predicting "best" wine comparatively.

## LDA: 

At 0.8 threshold, the model has the highest prediction accuracy of 69.57% for best wines. There is always a sacrifice. In this scenario, I am predicting at least 10 (16) best wine while minimizing the number of incorrect best wines; only 7 okay wines are misidentified as best. On the other hand, the model fails to capture the rest of the 562 best wines, which is a very high number. I think if we need to select the top 10 wine, we don't need to use threshold in this case, but rather rank purely based on the probability. However, if we used confusion matrix like we used for knn, the accuracy improves to be 77.29%. This makes me realize that there is no single way to determine the accuracy level of one model.

## Tree:

So, interestingly, the tree model is not able to identify the worst wine perhaps due to the very low number of worst wines. The confusion matrix says that the model has an accuracy level of 77.83%, though it fails to capture the worst wines. This comes close to the accuracy level of both the LDA and the kNN.

## Conclusion:
The accuracy level for all three models are pretty similar to each other, so I will have to make a decision weighing the costs and benefits of each one. I think I will choose LDA. kNN is very sensitive to tuning and it doesnt help that we have variables that have non-linear relationships and are clustered on one side. Also, our data is heavily skewed as we have way more okay wines than worst or best, which will certainly affect the predictions. For tree classification, the worst type of wine is not being captured which makes me believe its not a good option. Instead, I think LDA will help us lessen the dominance of okay wines, especially because it relies on probability distributions. I decided not to use threshold like I did earlier because we only care about the top 10 or worst 10 wines.

### Files

- [View the Report (PDF)](Homework%202%20Stats%200218.pdf)
- [HTML Report](Homework%202-%20STATS%200218%20copy.html)
- [Quarto Code (QMD)](Homework%202-%20STATS%200218.qmd)

