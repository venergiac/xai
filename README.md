# xai

Simple experiments of XAI = Explainable Artificial Intelligence


Sometime we use both terms Artificial Intelligence (AI) and Machine Learning (ML), but we say "AI" and we use Machine Learning, in the same way, we say "Explainable" but we refer to "Interpretable".

Although interpretability and explainability have been used interchangeably, there is a substantial difference. Explainable means completely human understandable. Interpretable is to describe the internals of a system in a way that is understandable to humans, but not necessarily in a complete way. So interpretable is the first step of explainable. Explainable models are interpretable by default, but the reverse is not always true.

In this simple noteboo we will WINE database to test features importance/perturbation and LIME



## Taxonomy of XAI

### Feature summary statistic
Many interpretation methods provide summary statistics for each feature. Some methods return a single number per feature, such as feature importance, or a more complex result, such as the pairwise feature interaction strengths, which consist of a number for each feature pair.
### Feature summary visualization
Most of the feature summary statistics can also be visualized. Some feature summaries are actually only meaningful if they are visualized and a table would be a wrong choice. The partial dependence of a feature is such a case. Partial dependence plots are curves that show a feature and the average predicted outcome. The best way to present partial dependences is to actually draw the curve instead of printing the coordinates.
### Model internals (e.g. learned weights)
The interpretation of intrinsically interpretable models falls into this category. Examples are the weights in linear models or the learned tree structure (the features and thresholds used for the splits) of decision trees. The lines are blurred between model internals and feature summary statistic in, for example, linear models, because the weights are both model internals and summary statistics for the features at the same time. Another method that outputs model internals is the visualization of feature detectors learned in convolutional neural networks. Interpretability methods that output model internals are by definition model-specific (see next criterion).
### Data point
This category includes all methods that return data points (already existent or newly created) to make a model interpretable. One method is called counterfactual explanations. To explain the prediction of a data instance, the method finds a similar data point by changing some of the features for which the predicted outcome changes in a relevant way (e.g. a flip in the predicted class). Another example is the identification of prototypes of predicted classes. To be useful, interpretation methods that output new data points require that the data points themselves can be interpreted. This works well for images and texts, but is less useful for tabular data with hundreds of features.
### Intrinsically interpretable model
One solution to interpreting black box models is to approximate them (either globally or locally) with an interpretable model. The interpretable model itself is interpreted by looking at internal model parameters or feature summary statistics.