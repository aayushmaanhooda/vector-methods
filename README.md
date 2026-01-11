# TF-IDF and BM25 Theory

## TF-IDF

**Term Frequency (TF)**: How often a word appears in a document
```
TF = (count of word in document) / (total words in document)
```

**Inverse Document Frequency (IDF)**: How rare a word is across all documents
```
IDF = log(total documents / documents containing the word)
```

**TF-IDF Score**: 
```
TF-IDF = TF × IDF
```

High score = word is frequent in document AND rare in corpus.

**Problem**: No saturation - word appearing 100 times gets 100× score. No document length normalization.

## BM25

Improves TF-IDF with:

1. **Saturation**: After enough repetitions, extra occurrences don't help much
2. **Document length normalization**: Adjusts for different document lengths
3. **Tunable parameters**: k1 (saturation) and b (length normalization)

**Formula**:
```
BM25 = IDF × (k1 + 1) × f(t,d) / (k1 × ((1-b) + b × |d|/avgdl) + f(t,d))
```

Where:
- f(t,d) = frequency of term in document
- |d| = document length
- avgdl = average document length
- k1 ≈ 1.2, b ≈ 0.75
