# 倒推指数与顺推指数的差异

> 原文:[https://www . geesforgeks . org/difference-inverted-index-forward-index/](https://www.geeksforgeeks.org/difference-inverted-index-forward-index/)

**[【倒排索引】](https://www.geeksforgeeks.org/inverted-index/)**

1.  It is a data structure that stores the mapping from words to documents or document sets, that is, it guides you from words to documents.
2.  The steps of building an inverted index are as follows:
    *   Take the document and gather all the words.
    *   Check each word, and if there is one, add a document reference to the index, otherwise create a new entry for the word in the index.
    *   Repeat the above steps for all documents and sort the words.
3.  Indexing is slow because it first checks whether words exist.
4.  Search is very fast.
5.  倒排索引示例:

    ```
    Word                              Documents
    hello                             doc1      
    sky                               doc1, doc3
    coffee                            doc2
    hi                                doc2
    greetings                         doc3                               

    ```

    它在索引中不存储重复的关键字。

6.  Real-life example of inverted index:
    *   The index at the back of the book.
    *   Reverse lookup

**正向索引:**

1.  It is a data structure that stores the mapping from documents to words, that is, it guides you from documents to words.
2.  The steps of establishing Forward index are:
    *   Get documents and collect all keywords.
    *   Append all keywords in the index entry of this document.
    *   Repeat the above steps for all documents.
3.  The index is quite fast because it only appends keywords when it moves forward.
4.  Search is quite difficult, because it has to look at every content of the index to retrieve all pages related to word.
5.  正向索引示例:

    ```
    Document                          Keywords
    doc1                              hello, sky, morning      
    doc2                              tea, coffee, hi
    doc3                              greetings, sky

    ```

    它在索引中存储重复的关键字。单词“sky”被存储多次。

6.  Real-life examples of Forward index:
    *   Catalogue in the book.
    *   DNS lookup

**正向索引和反向索引的相似度:**

*   Both are used to search for text in a document or document set.