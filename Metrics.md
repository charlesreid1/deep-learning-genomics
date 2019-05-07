# Metrics

## Receiver Operating Characteristic (ROC) Curve

The ROC curve is a way to visualize the tradeoff
between setting too **low** of a treshhold for the 
classification task, which results in many false
positives, and setting too **high** of a threshold
for the classification task, which resuts in many
false negatives.

The ROC curve helps visualize this tradeoff - the 
true positive rate is plotted against the false 
positive rate. As the threshold varies, the tradeoff
between the two will vary (hopefully increasing).

## ROC AUC (Area Under Curve)

The area under the ROC curve provides an indication 
of the model's ability to distinguish different
classes - the more area under the curve, the better
the model is at the classification task (that is,
the faster the true positive rate rises relative to
the false positive rate).

However, this is a global metric and as such is not
suitable to be evaluated continuously or to provide
an objective function to minimize.

