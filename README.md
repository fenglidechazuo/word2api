This repository contains the experiment data for "Bridging Semantic Gaps between Natural Languages and APIs with Word Embeddingn", including the semantic vectors generated by Word2API and the results for human judgements.

# Abstract

Developers increasingly rely on text matching tools to analyze the relation between natural language words and APIs.
However, semantic gaps, namely textual mismatches between words and APIs, negatively affect these tools. Previous studies have
transformed words or APIs into low-dimensional vectors for matching; however, inaccurate results were obtained due to the failure of
modeling words and APIs simultaneously. To resolve this problem, two main challenges are to be addressed: the acquisition of massive
words and APIs for mining and the alignment of words and APIs for modeling. Therefore, this study proposes Word2API to effectively
estimate relatedness of words and APIs. Word2API collects millions of commonly used words and APIs from code repositories to
address the acquisition challenge. Then, a shuffling strategy is used to transform related words and APIs into tuples to address the
alignment challenge. Using these tuples, Word2API models words and APIs simultaneously. Word2API outperforms baselines by
10%-49.6% of relatedness estimation in terms of precision and NDCG. Word2API is also effective on solving typical software tasks,
e.g., query expansion and API documents linking. A simple system with Word2API-expanded queries recommends up to 21.4% more
related APIs for developers. Meanwhile, Word2API improves comparison algorithms by 7.9%-17.4% in linking questions in
Question&Answer communities to API documents.

# Dictionary
We construct a semantic dictionary for natural language words and Java SE APIs. The dictionary is effective on semantic estimation between words and APIs. You can download the dictionary from the following path. Each line of the dictionary contains a word and its vector. Each line has 101 columns. The first column is a term (word or API). The other 100 columns represent a 100-dimensional vector generated by Word2API for this term.

>> [dictionary//java.zip](https://github.com/softw-lab/word2api/tree/master/dictionary/)

The dicionary is 120MB. We split it into three files "java.zip, java.z01, and java.z02". The dictionary can be visited after uncompressing the three files.

There is an example of the dictionary (the first 1,000 lines of it). You can visit it from the following path.

>> [dictionary//java-example.dic](https://github.com/softw-lab/word2api/tree/master/dictionary/)

An example (source code) to use the dictionary can also be found in the folder. The source code can calculate the similarity between a word and an API or a set of words and a set of APIs with the dictionary (see the method similarityOfTwoTerms and similarityOfTwoTermSets in W2ASimilarity.java). 

>> [dictionary//code-for-using-the-dic//src//org//oscarlab//word2api//](https://github.com/softw-lab/word2api/tree/master/dictionary/code-for-using-the-dic/src/org/oscarlab/word2api)


# Human Judgement
To evaluate the semantic relatedness between words and APIs, several human judgements are conducted. The judgements are subjective. We share the human judgement results for research. You can download the results from the following path.

>> [human//judgement.xlsx](https://github.com/softw-lab/word2api/tree/master/human/)

This file has three sheets:
- Sheet 1 includes the recommended APIs for the 50 query words and the human judgements for the relatedness of word-API pairs (supplement for Section 5.1.2);
- Sheet 2 includes the APIs recommended by every algorithms for a given query word (supplement for Section 5.1.2)
- Sheet 3 includes the questions (in Stack Overflow) we used to evaluate the task of API documents linking (supplement for Section 7)


