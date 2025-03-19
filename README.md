# CS572 - INFORMATION RETRIEVAL

## Formulae

**# Information Retrieval Formulas (Lecture 1 - Final Lecture)**

## **Lecture 1: Introduction to IR**
(No major formulas, just concepts)

---

## **Lecture 2: Indexing & Vector Space Retrieval Models**
### **Cosine Similarity (Vector Space Model)**
\[
\cos(\theta) = \frac{A \cdot B}{||A|| \cdot ||B||}
\]
where:
- \( A \cdot B \) = dot product of document and query vectors
- \( ||A||, ||B|| \) = magnitude of vectors

### **TF-IDF Weighting**
\[
\text{TF-IDF} = \text{TF} \times \log\left(\frac{N}{DF}\right)
\]
where:
- **TF** = Term Frequency in document
- **DF** = Number of documents containing the term
- **N** = Total number of documents

---

## **Lecture 3: Evaluation Metrics**
### **Precision & Recall**
\[
\text{Precision} = \frac{|\text{Relevant Docs} \cap \text{Retrieved Docs}|}{|\text{Retrieved Docs}|}
\]
\[
\text{Recall} = \frac{|\text{Relevant Docs} \cap \text{Retrieved Docs}|}{|\text{Relevant Docs}|}
\]

### **Mean Average Precision (MAP)**
\[
MAP = \frac{1}{|Q|} \sum_{q \in Q} AP(q)
\]
where:
- \( AP(q) \) = Average Precision for query \( q \)
- \( |Q| \) = Total number of queries

### **Discounted Cumulative Gain (DCG)**
\[
DCG_k = \sum_{i=1}^{k} \frac{rel_i}{\log_2(i+1)}
\]

### **Normalized DCG (nDCG)**
\[
nDCG_k = \frac{DCG_k}{IDCG_k}
\]

---

## **Lecture 4: Probabilistic Models**
### **Binary Independence Model (BIM)**
\[
RSV = \sum \log \frac{P(t_i | R)}{P(t_i | NR)}
\]

---

## **Lecture 5: BM25 & Language Models**
### **BM25 Ranking Formula**
\[
BM25 = \sum IDF \times \frac{TF \times (k_1 +1)}{TF + k_1 (1-b + b \frac{DL}{AVGDL})}
\]
where:
- \( k_1 \) = Term frequency scaling (1.2-2 default)
- \( b \) = Length normalization (default 0.75)

### **Jelinek-Mercer Smoothing**
\[
P_{JM}(w|d) = (1 - \lambda) P(w | d) + \lambda P(w | C)
\]

### **Dirichlet Smoothing**
\[
P_{Dir}(w | d) = \frac{TF + \mu P(w | C)}{DL + \mu}
\]

---

## **Lecture 6: Learning to Rank (LTR)**
### **Pointwise LTR**
- Predicts a **score** for each document individually

### **Pairwise LTR (RankNet Loss)**
\[
Loss = -\sum_{(d_i, d_j) \in P} \log \sigma(S(d_i) - S(d_j))
\]
where:
- \( d_i \) and \( d_j \) = Document pairs
- \( S(d) \) = Predicted score of document \( d \)

### **Listwise LTR (LambdaMART, NDCG Optimization)**
\[
nDCG_k = \frac{DCG_k}{IDCG_k}
\]

---

## **Lecture 7: Web Search & PageRank**
### **PageRank Formula**
\[
PR(A) = (1 - d) + d \sum \frac{PR(B)}{L(B)}
\]
where:
- \( d \) = Damping factor (default 0.85)
- \( L(B) \) = Number of outbound links from page \( B \)

---

## **Lecture 8: Web Crawling & Indexing**
### **Inverted Index**
- A **mapping** from terms → document IDs.
- Uses **compression techniques (delta encoding, front-coding)** to reduce storage.

---

## **Lecture 9: Online Learning to Rank (OLTR)**
### **Dueling Bandit Gradient Descent (DBGD)**
- Optimizes ranking **via real-time user feedback**.
- Uses **exploration (trying new rankings) vs. exploitation (keeping best-known rankings).**

---

## **Lecture 10: Personalized Search & Recommender Systems**
### **Collaborative Filtering (CF)**
\[
score(u, i) = \sum_{v \in N(u)} w_{uv} r(v, i)
\]
where:
- \( u, v \) = Users
- \( w_{uv} \) = Similarity between users
- \( r(v, i) \) = Rating of item \( i \) by user \( v \)

### **Content-Based Filtering (TF-IDF Similarity for Recommendations)**
\[
sim(A, B) = \frac{\sum w_A w_B}{||A|| ||B||}
\]


