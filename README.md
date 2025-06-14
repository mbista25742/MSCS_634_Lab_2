# Wine Classification Lab - KNN vs RNN

## Purpose
The purpose of this lab was to evaluate and compare the classification performance of K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) using the Wine dataset from sklearn. By experimenting with different values of `k` and `radius`, the lab aimed to analyze how parameter tuning impacts model accuracy and to determine which algorithm performs better under various conditions.

## Key Insights

- **KNN consistently outperformed RNN** across most parameter settings, with its best accuracy reaching **0.8056** for `k = 5`, `11`, `15`, and `21`.
- **KNN accuracy was highest at lower k values**, peaking at `k = 5`, and showed no improvement beyond that.
  - KNN Accuracy (k=1): 0.7778  
  - KNN Accuracy (k=5): 0.8056  
  - KNN Accuracy (k=11): 0.8056  
  - KNN Accuracy (k=15): 0.8056  
  - KNN Accuracy (k=21): 0.8056  

- **RNN initially showed very poor performance** with high radius values (350–600), resulting in an accuracy of only **0.3889** across all those settings.
  - RNN Accuracy (radius=350 to 600): 0.3889 (no variation)

- However, testing with a **much smaller radius (5)** led to a **significant improvement**, achieving an accuracy of **0.8611**, the highest among all models tested:
  - RNN Accuracy (radius=5): 0.8611  

- This sharp improvement confirmed that the earlier radius values were far too large, likely due to a mismatch with the scale of feature values.

## Challenges and Decisions

- A key challenge was the **initial poor performance of RNN**, which was caused by the selection of overly large radius values. The radius values (350–600) were too broad given the dataset's feature scale, leading to ineffective neighbor selection and poor model accuracy.
- **Feature scaling was not applied**, which affected distance-based models like RNN. Despite this, KNN was still relatively stable, while RNN required fine-tuned radius values.
- A decision was made to test with a **much smaller radius (5)**, which revealed the true potential of RNN on this dataset.
- KNN was **more straightforward to tune** and less sensitive to parameter choice, making it a more reliable choice without scaling.
- RNN can outperform KNN, but **only with precise tuning and proper distance calibration**, such as scaling features and choosing a radius that reflects the true structure of the data.

---

## Conclusion
While KNN delivered solid and consistent accuracy with minimal tuning, RNN demonstrated its potential to outperform KNN — but only when the radius was carefully adjusted to match the dataset's scale. Feature scaling and parameter sensitivity are crucial when working with distance-based classifiers like RNN.

