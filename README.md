# MicrobeClassification

<img src="images/Screen Shot 2022-08-11 at 7.11.09 PM.png" align="middle" width="3000"/>

Bacteria have been growing increasingly more antibiotic-resistant over the years as bacterial genes adapt to the weaknesses that make antibiotics effective. As a solution to these adaptations, scientists have began using genetic sequencing to identify and battle against the genes in question. However, these sequencing techniques are meticulous and sometimes, they are not quick enough to save patient lives from infections. As a result, if we can use AI to quickly identify these microbes, more lives may be saved. 

This model is trained to detect other microbes, but in the future can be scaled for bacterial uses. Datasets containing the following characteristics can be trained with this model: 'Solidity', 'Eccentricity', 'EquivDiameter', 'Extrema', 'FilledArea','Extent', 'Orientation', 'EulerNumber', 'BoundingBox1', 'BoundingBox2','BoundingBox3', 'BoundingBox4', 'ConvexHull1', 'ConvexHull2','ConvexHull3', 'ConvexHull4', 'MajorAxisLength', 'MinorAxisLength','Perimeter', 'ConvexArea', 'Centroid1', 'Centroid2', 'Area', 'raddi'

Source of code: https://www.kaggle.com/datasets/sayansh001/microbes-dataset

## QNA
#### Dataset questions
**How would we scale this microorganism detection model to detect bacteria?**
We can build a similar multi-class classifier model based on a bacterial dataset with similar numerical features.

**What is the point of using StandardScaler for each column?**
Each of the different features have different expected ranges from each other. This means that it would not make sense to treat equivalent values that are in different columns as the same value. To clarify, I can give an example about weight and height. Weight woud have an expected range of 80-300 (lb) while height would have an expected range of 50-90. A value of 70 would have a different meaning in the weight column that it would in the height column. In the weight column, 70 would be an outlier while in the height column it would the mean. A similar situation exists for the values in each of the columns in this dataset, which is why I used StandardScaler.

#### Algorithm Questions
**Why is LightGBM faster than Decision Trees for this model?**
Unlike other tree-based algorithms that grow horizontally, LightGBM grows vertically. This means that LightGBM grows *leafwise* while other tree-based algorithms grow *level-wise*. Leaf-wise growth can reduce more loss than level-wise growth.

**What's the point of gradient boosting?**
Gradient boosting keeps overfitting in check and combines results along the way, increasing accuracy.

**Will LightGBM be as efficient in bigger or smaller datasets?**
In smaller datasets, LightGBM may lead to overfitting, as it is optimized for bigger and heavier dataloads. This also means that LightGBM would be able to handle heavier workloads in such models.
