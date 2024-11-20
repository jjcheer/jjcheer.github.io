## Content List
[1. Business Intelligence with Weka](https://jjcheer.github.io)   
[2. LPY01](lpy01.md)   
[3. LPY02](lpy02.md)
## 欢迎来到我的主页。

It's a beginners Business intelligence recording sites. In this site, I use WEKA, some times use R to do some business analytics practice and write down some tips in interacting with the software, WEKA and R.

### Classify

1. Processing the imbalance data with WEKA.

There are several ways to treat with imbalance data sets. The solutions can be divided into 2 categories: treating the process and treating the results.

- Treating process.
We can use resamplint methodologies to increase the monority categories, for example, the SMOTE sampling to increase the minority; or we can decrease the majority. Though some scholars have discussed the weaknesses of these kinds of methods, but it provides ways to try.

- Treating results.
We can use the cost-sensitive evaluation to penalize the wrong categories. some times, if we want to penalize the FP (e.g. in the SPAM mail detection), then we can set the cost to a higher proportion. if we want to penallize FN (e.g. in the Cancer detection), we can set the cost of FN to a higher proportion. 

Though this kind of method is not soly for the imbalance catagory problem, actually, its intention is to consider the importance of different errors. but sometimes we use it to solve the imbalance classify problems.

2. How to operate in WEKA.
If we use the J48 directly, and Choose J48 in the "choose" manually, and check "cost-sensitive evaluation" and set... the cost matrix in the cost matrix editor. you will find you setting will have no influence on the results.

the reason lies in that in J48, the main principle in constructing the tree is "entropy deduction ratio", and the cost is not under consideration. So you have to set the cost to the main principle by choosint a meta cost sensitive classifier. in this process, you can also choose J48 as you classifier in the process.

When using this set to PPD data, we get the results like this:

=== Summary ===

Correctly Classified Instances        7314               81.2667 %
Incorrectly Classified Instances      1686               18.7333 %
Kappa statistic                          0.0491
Total Cost                            6357     
Average Cost                             0.7063
Mean absolute error                      0.3909
Root mean squared error                  0.4172
Relative absolute error                287.9311 %
Root relative squared error            160.2729 %
Total Number of Instances             9000     
```
=== Detailed Accuracy By Class ===

                 TP Rate  FP Rate  Precision  Recall   F-Measure  MCC      ROC Area  PRC Area  Class
                 0.860    0.789    0.933      0.860    0.895      0.053    0.559     0.937     0
                 0.211    0.140    0.106      0.211    0.142      0.053    0.559     0.090     1
Weighted Avg.    0.813    0.741    0.872      0.813    0.840      0.053    0.559     0.875     

```

```
=== Confusion Matrix ===

    a    b   <-- classified as
 7175 1167 |    a = 0
  519  139 |    b = 1

=== we correctly get 139 FP items.
```

