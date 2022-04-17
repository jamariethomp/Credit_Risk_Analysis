# Credit Risk Analysis

## Overview of the loan prediction risk analysis:

Determining the frequency of credit risk in a large population is a task that may be well-suited to machine learning. Machine learning can utilize algorithms to help us predict an outcome given a certain set of factors, and thus may help us determine the potential for high credit risk in an individual. This analysis seeks to employ different techniques to train and evaluate models with unbalanced classes, which applies to credit risk since there are many more people in the "low-risk" category than in the "high-risk" category. Using a credit card credit dataset from LendingClub, a peer-to-peer lending services company, the data has been resampled and applied to several differnent machine learning models, including RandomOverSampler, SMOTE,  ClusterCentroids, SMOTEENN, BalancedRandomForestClassifier, and EasyEnsembleClassifier.

 ## Results:

- RandomOverSampler

This model's accuracy score acheives a rating of 62%, which would be too low for our purposes:

 ![RandomOversampler_balanced_accuracy](https://user-images.githubusercontent.com/94264643/163697712-b32467fe-3391-48b4-b37c-091cb3b36426.png)
 
The classification report indicates a wide gap in the precision between low risk and high risk lendees, and the sensitivity (recall) rates hover around 0.65:

![RandomOversampler_classification_report](https://user-images.githubusercontent.com/94264643/163697713-261e22e4-84ff-4a4a-8e42-bbf4096c708e.png)

As such, this would not be an ideal model for our purposes.

- SMOTE Oversampling

SMOTE reaches an accuracy score of 65%, which is not much better than our RandomOverSampler model:

![SMOTE_balanced_accuracy](https://user-images.githubusercontent.com/94264643/163697721-5147708d-5d7b-48ec-ad08-905c9c0be454.png)

The classifcation report indicates an even wider gap in precision and an average recall of 0.66:

![SMOTE_classification_report](https://user-images.githubusercontent.com/94264643/163697722-1885a157-7cf5-4e0e-9694-2e8460a54f9d.png)

As the with the previous model, this would not be suitable for our needs.

- ClusterCentroids Undersampling

Our ClusterCentroids undersampling model acheives a disappointing 51% accuracy score:

![Undersampling_balanced_accuracy](https://user-images.githubusercontent.com/94264643/163697740-0f9b8fba-40d6-46aa-9b79-1f187a8daa5a.png)

The classification report indicates yet another wide gap in precision between high-risk and low-risk lendees and a precision of 0.44:

![Undersampling_classification_report](https://user-images.githubusercontent.com/94264643/163697744-327cb454-db60-4586-84e0-150dfcf127e8.png)

This model would also not be suitable in predicting credit score ratings.

- SMOTEENN Over-and-Undersampling

The balanced accuracy rate in our SMOTEENN model reaches a rate of 62%:

![SMOTEENN_balanced_accuracy](https://user-images.githubusercontent.com/94264643/163697748-6a72b1fb-6774-4141-b191-a072f8298157.png)

Another wide gap in precision and a recall of 0.54 indicate low accuracy even further:

![SMOTEENN_classification_report](https://user-images.githubusercontent.com/94264643/163697750-6a81cdf2-c6e9-41fe-aa4d-0cab46482a2f.png)

SMOTEENN is not our go-to model for this analysis.

- BalancedRandomForestClassifier

Our BalancedRandomForestClassifier acheives a more promising accuracy rate of 78%:

![BalancedRandomForestClassifier_balanced_accuracy](https://user-images.githubusercontent.com/94264643/163697753-f22f89d1-1fe0-4ff6-ac38-711672797c98.png)

There is still a large gap in the precision of our low-risk and high-risk applicants, but the recall rate comes in at 0.87:

![BalancedRandomForestClassifier_classification_report](https://user-images.githubusercontent.com/94264643/163697754-999715e4-6b09-4533-bbcf-0bbc02cb20a6.png)

- EasyEnsembleClassifier

Our EasyEnsembleClassifier achieves a promising accuracy rate of 93%:

![EasyEnsembleClassifier_balanced_accuracy](https://user-images.githubusercontent.com/94264643/163697759-be7e96a8-a909-4429-8f99-e0de32f71bd7.png)

The gap in precision is still large, but begining to close, with this model; a recall rate of 0.94 is also promising:
![EasyEnsembleClassifier_classification_report](https://user-images.githubusercontent.com/94264643/163697762-9157efee-e87c-42ca-8973-e82f87f7adf9.png)

The accuracy here might not be as high as we would need it to be in order to determine a person's credit risk, but among the models tested, it is the best.

## Summary:

For the most part, our models do not offer us enough confidence that a particular applicant might have a high credit risk based purely on the factors provided. With the information and machine learning models provided, it is simply too difficult to determine high risk where there is not enough data from high-risk applicants to support an effective algorithm.

While the models at hand should not be used alone to determine credit risk, the EasyEnsembleClassifier model is rather accurate, and may be used as a supplement in addition to more information in determining credit risk.
