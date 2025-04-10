# ArcFace Face Verification Evaluation
This project evaluates the performance of the **ArcFace** face recognition model on verifying whether two face images belong to the same person.

## How It Works 
1. **Data Preparation**
  - The dataset is based on [Labeled Faces in the Wild (LFW)](https://www.kaggle.com/datasets/jessicali9530/lfw-dataset)
2. **Image Selection**
  - For each person, the code selects **up to 5 images** (to limit the total number of comparisons).
3. **Model Loading**
  - The **ArcFace model** (`buffalo_l`) is automatically loaded using the [InsightFace](https://github.com/deepinsight/insightface) library.
4. **Face Embedding Extraction**
  - Each image is passed to the ArcFace model.
5. **Similarity Comparison**
  - Each image pair’s embeddings are compared using **cosine similarity**.
  - If the similarity score is higher than a chosen threshold (default: `0.6`), the pair is classified as a **Match** (same person). Otherwise, it is considered **No Match**.
6. **Result Reporting**
  - For each pair, the system prints the similarity score and the result.
  - After evaluating all pairs, a summary is displayed:
    - Total number of evaluated pairs
    - Number of correct matches
    - Number of false negatives (missed matches)
    - Overall accuracy
