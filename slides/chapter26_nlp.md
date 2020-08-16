---
type: slides
---

# NLP

Notes: Text at the end of a slide prefixed like this will be displayed as
speaker notes on the side. Slides can be separated with a divider: ---.

--- 

# Why is this a seperate section?

Dealing with text data is it's own section, and is definitely much larger than could be shown before.

Generally speaking when we get text data we need to convert them into a format that a model can use them as.

---

# TFIDF

TFIDF stands for Term Frequency-Inverse Document Frequency and is used to evaluate how important a word in a document to a collection or corpus.

The importance increases proportionally to the number of times a word appears in the document but is offset by the frequency in the corpus.

One of the simplest term ranking processes is summing up the TFIDF for a given word (or combination).

TF(t) = (Number of times term t appears in the document) / (total number of terms in the document)

IDF(t) = Log_e(Total number of documents / Number of documents with t in it)

TFIDF = TF(t) * IDF(t)

---

