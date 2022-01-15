# DonorsChoose.org-Application-Screening
## Introduction 
DonorsChoose.org receives hundreds of thousands of project proposals each year for classroom projects in need of funding. Right now, a large number of volunteers is needed to manually screen each submission before it's approved to be posted on the DonorsChoose.org website.The goal of the competition is to predict whether or not a DonorsChoose.org project proposal submitted by a teacher will be approved, using the text of project descriptions as well as additional metadata about the project, teacher, and school. DonorsChoose.org can then use this information to identify projects most likely to need further review before approval.</br>

#### Models 
I used various Models such as Naive Bayes, LSTM, Descion Tree, Xgboost. Following tables represents the performances of various 


**Naive Bayes**
```
+------------+-------------+-----------------------+--------------------+
| Vectorizer |    Model    | Alpha:Hyper Parameter |      Test-AUC      |
+------------+-------------+-----------------------+--------------------+
|    BOW     | Naive Bayes |         1e-05         | 0.7391361406003414 |
|   TFIDF    | Naive Bayes |         5e-05         | 0.7233254695385676 |
+------------+-------------+-----------------------+--------------------+
```


**Descion Tree and Logistic Regression**
```
+------------+---------------------+---------------------------------------+--------------------+
| Vectorizer |        Model        |               Parameters              |      Test-AUC      |
+------------+---------------------+---------------------------------------+--------------------+
|   TFIDF    |    Decision tree    | max_depth :10 ,min_samples_split: 500 | 0.6392734792904451 |
| TFIDF W2V  |    Decision tree    | max_depth :10 ,min_samples_split :500 | 0.6276350250723042 |
|   TFIDF    | Logistic regression |           C:10 , penalty: l1          | 0.6771386281717325 |
+------------+---------------------+---------------------------------------+--------------------+

```

**Xgboost**
```
+----------------------------------------+---------+-------------------------------------+--------------------+
|               Vectorizer               |  Model  |              Parameters             |      Test-AUC      |
+----------------------------------------+---------+-------------------------------------+--------------------+
| TFIDF +Response coding+sentiment_score | XGboost | max_depth :3 ,colsample_bytree: 0.1 | 0.6041440240532883 |
|       TFIDF W2V+Response coding        | XGboost | max_depth :3 ,colsample_bytree :0.1 | 0.6029916604726717 |
+----------------------------------------+---------+-------------------------------------+--------------------+
```
**LSTM**
In LSTM I used two Models 
[<img src="image.png" width="250"/>](image.png)

