### Face Recognition Loss Functions

| Loss Function           | Purpose | Formula | Key Points |
|-------------------------|---------|---------|------------|
| **Triplet Loss**        | Ensures that the distance between an anchor and a positive example is smaller than the distance between the anchor and a negative example | ${\text{Triplet Loss} = \max(d(a, p) - d(a, n) + \text{margin}, 0)}$ <br><br> *where:* <br> $d(a, p)$: Distance between anchor $a$ and positive $p$ <br> $d(a, n)$: Distance between anchor $a$ and negative $n$ <br> $\text{margin}$: Margin to ensure separation | - Effective for learning embeddings <br>- Requires careful selection of triplets |
| **Contrastive Loss**    | Encourages similar pairs to be close and dissimilar pairs to be far apart | ${\text{Contrastive Loss} = y \cdot d^2 + (1 - y) \cdot \max(\text{margin} - d, 0)^2}$ <br><br> *where:* <br> $d$: Distance between two embeddings <br> $y$: Binary label (1 for similar, 0 for dissimilar) <br> $\text{margin}$: Margin to separate dissimilar pairs | - Directly compares pairs <br>- Can be sensitive to the choice of margin |
| **Center Loss**         | Helps to minimize intra-class variation by learning a center for each class | ${\text{Center Loss} = \frac{1}{2} \sum_{i=1}^N \|f(x_i) - c_{y_i}\|^2}$ <br><br> *where:* <br> $f(x_i)$: Embedding of the $i$-th sample <br> $c_{y_i}$: Center of class $y_i$ <br> $N$: Number of samples | - Improves class center alignment <br>- Often used in conjunction with softmax loss |
| **Softmax Loss**        | Commonly used with neural networks to classify faces into predefined classes | ${\text{Softmax Loss} = -\sum_{i=1}^N \log\left(\frac{\exp(\text{score}_{i, y_i})}{\sum_{j=1}^M \exp(\text{score}_{i, j})}\right)}$ <br><br> *where:* <br> $\text{score}_{i, y_i}$: Score for class $y_i$ for the $i$-th sample <br> $M$: Number of classes <br> $N$: Number of samples | - Widely used for classification <br>- Suitable for multi-class problems |

---

### Face Recognition Metrics

| Metric                   | Purpose | Formula | Key Points |
|--------------------------|---------|---------|------------|
| **Accuracy**             | Measures the overall correctness of face recognition | ${\text{Accuracy} = \frac{\text{TP} + \text{TN}}{\text{TP} + \text{TN} + \text{FP} + \text{FN}}}$ <br><br> *where:* <br> $\text{TP}$: True Positives <br> $\text{TN}$: True Negatives <br> $\text{FP}$: False Positives <br> $\text{FN}$: False Negatives | - Simple and intuitive <br>- Can be misleading with imbalanced datasets |
| **Precision**            | Measures the accuracy of positive face recognition predictions | ${\text{Precision} = \frac{\text{TP}}{\text{TP} + \text{FP}}}$ <br><br> *where:* <br> $\text{TP}$: True Positives <br> $\text{FP}$: False Positives | - Important when the cost of false positives is high |
| **Recall (Sensitivity)** | Measures the ability to identify all correct face identities | ${\text{Recall} = \frac{\text{TP}}{\text{TP} + \text{FN}}}$ <br><br> *where:* <br> $\text{TP}$: True Positives <br> $\text{FN}$: False Negatives | - Important when the cost of false negatives is high |
| **F1 Score**             | Harmonic mean of precision and recall | ${\text{F1 Score} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}}$ <br><br> *where:* <br> $\text{Precision}$: Precision <br> $\text{Recall}$: Recall | - Balances precision and recall <br>- Useful for imbalanced datasets |
| **Mean Average Precision (mAP)** | Measures the average precision across all classes | ${\text{mAP} = \frac{1}{N} \sum_{i=1}^N \text{AP}_i}$ <br><br> *where:* <br> $\text{AP}_i$: Average Precision for class $i$ <br> $N$: Number of classes | - Provides an aggregate measure of precision <br>- Useful for evaluating overall performance |
| **Cosine Similarity**    | Measures similarity between face embeddings | ${\text{Cosine Similarity} = \frac{f(x_1) \cdot f(x_2)}{\|f(x_1)\| \|f(x_2)\|}}$ <br><br> *where:* <br> $f(x_1)$: Embedding vector for face 1 <br> $f(x_2)$: Embedding vector for face 2 | - Useful for comparing embeddings <br>- Ranges between -1 and 1 |
