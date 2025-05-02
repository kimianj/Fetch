# Fetch

## 📌 Tasks Overview

### ✅ Task 1: Sentence Transformer Implementation
- Used the `sentence-transformers` library with the pre-trained model `all-MiniLM-L6-v2`.
- Encoded sample sentences into 384-dimensional fixed-length embeddings.
- Applied manual L2 normalization for cosine similarity and clustering use cases.
- Used mean pooling over token embeddings as the pooling strategy.

### ✅ Task 2: Multi-Task Learning Expansion
- Extended the sentence transformer to handle:
  - **Task A**: Sentence topic classification (e.g., Tech, Animal, Weather)
  - **Task B**: Sentiment analysis (Negative, Neutral, Positive)
- Implemented a shared transformer encoder with two task-specific classification heads.
- Combined task losses to train both heads jointly.

### ✅ Task 3: Training Considerations & Transfer Learning
- Explored different freezing strategies:
  - Freezing the entire network
  - Freezing only the backbone
  - Freezing only one task head
- Used a phased fine-tuning approach:
  - First trained task heads independently
  - Then unfroze the encoder for joint fine-tuning
- Leveraged `all-MiniLM-L6-v2` for transfer learning due to its performance and efficiency.

### ✅ Task 4: Multi-Epoch Training Loop (BONUS)
- Simulated training using synthetic sentence data and labels.
- Computed and tracked **accuracy** and **F1 scores** for both tasks.
- Demonstrated steady learning improvements across epochs.
