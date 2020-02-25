# xai

Simple experiments of XAI = Explainable Artificial Intelligence

![](https://1.bp.blogspot.com/-wJ2iOmJmSXo/XjPsp1AZceI/AAAAAAAAM9E/lb25nmKM3nsuqqInetF6L43CKbVK6PMHACLcBGAsYHQ/s1600/Screen%2BShot%2B2020-01-31%2Bat%2B08.01.23.png)

Sometime we use both terms Artificial Intelligence (AI) and Machine Learning (ML), but we say "AI" and we use Machine Learning, in the same way, we say "Explainable" but we refer to "Interpretable".

Although interpretability and explainability have been used interchangeably, there is a substantial difference. Explainable means completely human understandable. Interpretable is to describe the internals of a system in a way that is understandable to humans, but not necessarily in a complete way. So interpretable is the first step of explainable. Explainable models are interpretable by default, but the reverse is not always true.

In this simple noteboo we will WINE database to test features importance/perturbation and LIME



## Taxonomy of XAI

### Feature summary statistic
Many interpretation methods provide summary statistics for each feature. Some methods return a single number per feature, such as feature importance, or a more complex result, such as the pairwise feature interaction strengths, which consist of a number for each feature pair.
### Feature summary visualization
Most of the feature summary statistics can also be visualized. Some feature summaries are actually only meaningful if they are visualized and a table would be a wrong choice. The partial dependence of a feature is such a case. Partial dependence plots are curves that show a feature and the average predicted outcome. The best way to present partial dependences is to actually draw the curve instead of printing the coordinates.

![](https://1.bp.blogspot.com/-GktyJ7w5JXk/XlVG4LJ1VeI/AAAAAAAANJo/u0uVnh4h9B40wF0L60t2pZpI5798JiHiwCLcBGAsYHQ/s320/feature_importance.png)

### Model internals (e.g. learned weights)
The interpretation of intrinsically interpretable models falls into this category. Examples are the weights in linear models or the learned tree structure (the features and thresholds used for the splits) of decision trees. The lines are blurred between model internals and feature summary statistic in, for example, linear models, because the weights are both model internals and summary statistics for the features at the same time. Another method that outputs model internals is the visualization of feature detectors learned in convolutional neural networks. Interpretability methods that output model internals are by definition model-specific (see next criterion).
### Data point
This category includes all methods that return data points (already existent or newly created) to make a model interpretable. One method is called counterfactual explanations. To explain the prediction of a data instance, the method finds a similar data point by changing some of the features for which the predicted outcome changes in a relevant way (e.g. a flip in the predicted class). Another example is the identification of prototypes of predicted classes. 


![](https://1.bp.blogspot.com/-O8YRaSIgEZA/XlVICiccP5I/AAAAAAAANJw/mCw8MLq9JpcLjbCgrOS9PQcmNjFZdigoACLcBGAsYHQ/s320/feature_permutation.png)

To be useful, interpretation methods that output new data points require that the data points themselves can be interpreted. This works well for images and texts, but is less useful for tabular data with hundreds of features.

![](https://1.bp.blogspot.com/-wUQWieyHmrI/XlV2LciuYUI/AAAAAAAANKI/JPHZr2EzVnAINxRPilqkkLJJBCByIOjoACLcBGAsYHQ/s1600/Screen%2BShot%2B2020-02-25%2Bat%2B20.31.37.png)


### Intrinsically interpretable model
One solution to interpreting black box models is to approximate them (either globally or locally) with an interpretable model. The interpretable model itself is interpreted by looking at internal model parameters or feature summary statistics.