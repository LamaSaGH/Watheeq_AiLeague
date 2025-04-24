# ArcFace Face Verification Evaluation

We evaluates the performance of the **ArcFace** deep face recognition model on verifying whether two images belong to the same person. The evaluation was conducted using a subset of the **LFW (Labeled Faces in the Wild)** dataset.



---

## 📁 Dataset

- **Source**: LFW DeepFunneled
- **Selection Criteria**:
  - For *same-person* testing: individuals with at least two clear images were selected.
  - For *different-person* testing: individuals with only one image were paired sequentially with others.
- **Total evaluated pairs**: `1049`
  - Same-person pairs: `420`
  - Different-person pairs: `629`

---

## ⚙️ How It Works

### 1. **Model**
- ArcFace (`buffalo_l`) loaded via `insightface` library.

### 2. **Embedding Extraction**
- For each image:
  - Load and detect face using ArcFace.
  - Extract 512-dimension embedding (if a face is detected).



- Threshold: `0.6`
  - Similarity > 0.6 → Match
  - Otherwise → No Match

### 4. **Evaluation Logic**
- Same-person pairs: compare first 2 images of a person.
- Different-person pairs: match between two people with only 1 image each.

### 5. **Metrics**
- Confusion matrix
- Classification report (precision, recall, f1-score, accuracy)

---

## ✅ Results

- **Correct matches**: `1045` / `1049`
- **Accuracy**: `99.52%`


