# Information Retrieval Formulas (Lecture 1 - Final Lecture)

## **Lecture 1: Introduction to IR**
(No major formulas, just concepts)

---

## **Lecture 2: Indexing & Vector Space Retrieval Models**
### **Cosine Similarity (Vector Space Model)**
cos(θ) = (A ⋅ B) / (||A|| ⋅ ||B||)
where:
- A ⋅ B = dot product of document and query vectors
- ||A||, ||B|| = magnitude of vectors

### **TF-IDF Weighting**
TF-IDF = TF × log(N / DF)
where:
- TF = Term Frequency in document
- DF = Number of documents containing the term
- N = Total number of documents

---

## **Lecture 3: Evaluation Metrics**
### **Precision & Recall**
Precision = |Relevant Docs ∩ Retrieved Docs| / |Retrieved Docs|
Recall = |Relevant Docs ∩ Retrieved Docs| / |Relevant Docs|

### **Mean Average Precision (MAP)**
MAP = (1 / |Q|) ∑ AP(q) for all q in Q
where:
- AP(q) = Average Precision for query q
- |Q| = Total number of queries

### **Discounted Cumulative Gain (DCG)**
DCG_k = ∑ (rel_i / log2(i+1)) for i = 1 to k

### **Normalized DCG (nDCG)**
nDCG_k = DCG_k / IDCG_k

---

## **Lecture 4: Probabilistic Models**
### **Binary Independence Model (BIM)**
RSV = ∑ log(P(t_i | R) / P(t_i | NR))

---

## **Lecture 5: BM25 & Language Models**
### **BM25 Ranking Formula**
BM25 = ∑ IDF × [(TF × (k1 +1)) / (TF + k1 (1-b + b (DL / AVGDL)))]
where:
- k1 = Term frequency scaling (1.2-2 default)
- b = Length normalization (default 0.75)

### **Jelinek-Mercer Smoothing**
P_JM(w|d) = (1 - λ) P(w | d) + λ P(w | C)

### **Dirichlet Smoothing**
P_Dir(w | d) = (TF + μ P(w | C)) / (DL + μ)

---

## **Lecture 6: Learning to Rank (LTR)**
### **Pointwise LTR**
- Predicts a score for each document individually

### **Pairwise LTR (RankNet Loss)**
Loss = -∑ log σ(S(d_i) - S(d_j)) for all (d_i, d_j) in P
where:
- d_i and d_j = Document pairs
- S(d) = Predicted score of document d

### **Listwise LTR (LambdaMART, NDCG Optimization)**
nDCG_k = DCG_k / IDCG_k

---

## **Lecture 7: Web Search & PageRank**
### **PageRank Formula**
PR(A) = (1 - d) + d ∑ (PR(B) / L(B))
where:
- d = Damping factor (default 0.85)
- L(B) = Number of outbound links from page B

---

## **Lecture 8: Web Crawling & Indexing**
### **Inverted Index**
- A mapping from terms → document IDs.
- Uses compression techniques (delta encoding, front-coding) to reduce storage.

---

## **Lecture 9: Online Learning to Rank (OLTR)**
### **Dueling Bandit Gradient Descent (DBGD)**
- Optimizes ranking via real-time user feedback.
- Uses exploration (trying new rankings) vs. exploitation (keeping best-known rankings).

---

## **Lecture 10: Personalized Search & Recommender Systems**
### **Collaborative Filtering (CF)**
score(u, i) = ∑ w_uv r(v, i) for all v in N(u)
where:
- u, v = Users
- w_uv = Similarity between users
- r(v, i) = Rating of item i by user v

### **Content-Based Filtering (TF-IDF Similarity for Recommendations)**
sim(A, B) = (∑ w_A w_B) / (||A|| ||B||)

---

## **Final Notes:**
✔ BM25, TF-IDF, and Cosine Similarity are key ranking functions.
✔ LTR improves ranking using machine learning.
✔ PageRank determines static importance of web pages.
✔ Recommender systems use collaborative & content-based filtering.

