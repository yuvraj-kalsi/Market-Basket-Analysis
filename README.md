
# 🚀 Market Basket Analysis

**`In this Notebook we would learn`** 
​
* What is Association Rule Learning? ​
* How Apriori works ?
* Implementing Apriori With Python

## Problem Statement :
When we go grocery shopping, we often have a standard list of things to buy. Each shopper has a distinctive list, depending on one’s needs and preferences. A housewife might buy healthy ingredients for a family dinner, while a bachelor might buy beer and chips. Understanding these buying patterns can help to increase sales in several ways. If there is a pair of items, X and Y, that are frequently bought together:

* Both X and Y can be placed on the same shelf, so that buyers of one item would be prompted to buy the other.

* Promotional discounts could be applied to just one out of the two items.

* Advertisements on X could be targeted at buyers who purchase Y.

* X and Y could be combined into a new product, such as having Y in flavors of X.

## What is Association Rule Learning?

Association Rule Learning is rule-based learning for identifying the association between different variables in a database. **One of the best and most popular examples of Association Rule Learning is the Market Basket Analysis**. The problem analyses the association between various items that has the highest probability of being bought together by a customer.

For example, the association rule, {bread, butter} => {milk} says that a person who has got both bread and butter in his or her basket has a high probability of buying milk also.

## How Apriori works ?

To construct association rules between elements or items, the algorithm considers 3 important factors:
```bash
  Support
  Confidence
  Lift
```
![Img](https://annalyzin.files.wordpress.com/2016/04/association-rule-support-table.png?w=503&h=447)

**Support:**

The support of item I is defined as the ratio between the number of transactions containing the item I by the total number of transactions expressed as :

![Logo](https://miro.medium.com/max/403/0*pyOADkeaWyrVP2ft.png)

It indicates how popular an itemset is, as measured by the proportion of transactions in which an itemset appears. In Table above, support of **{apple}** is 4 out of 8, or 50%. Itemsets can also contain multiple items. For instance, the support of **{apple, beer, rice}** is 2 out of 8, or 25%.

**Confidence:**

This is measured by the proportion of transactions with item I1, in which item I2 also appears. The confidence between two items I1 and I2,  in a transaction is defined as the total number of transactions containing both items I1 and I2 divided by the total number of transactions containing I1.

![conf](https://miro.medium.com/max/576/1*50GI4dR58MnhwBP9dw6nFQ.png)

It says how likely item Y is purchased when item X is purchased, expressed as **{X -> Y}**. This is measured by the proportion of transactions with item X, in which item Y also appears. In Table, the confidence of **{apple -> beer}** is 3 out of 4 or 75%.

**Lift:**

Lift is the ratio between the support of item I1 and I2 and product of support I1 and support I2.

![lift](http://www.dataminingapps.com/wp-content/uploads/2017/03/lift.png')

It says how likely item Y is purchased when item X is purchased, while controlling for how popular item Y is. In Table, the lift of **{apple -> beer}** is 1, which implies no association between items. A lift value greater than 1 means that item Y is likely to be bought if item X is bought, while a value less than 1 means that item Y is unlikely to be bought if item X is bought.

## Implementing Apriori Algorithm

Dataset used in the program: 🔗[Groceries](https://www.kaggle.com/datasets/shrikantuppin/groceries)

```bash
The dataset contains a list of transactions and the items purchased in each transaction in a Super-Market.
```

Libraries used in the program: 

* [NumPy](https://numpy.org/doc/stable/) and [Pandas](https://pandas.pydata.org/docs/) - Data Manipulation
* [CSV Reader](https://docs.python.org/3/library/csv.html) - Reading the dataset
* [MLXtend](https://rasbt.github.io/mlxtend/) - Apriori Algorithm

Output:

![result](https://github.com/yuvraj-kalsi/Market-Basket-Analysis/assets/84912620/7326c27f-9b8a-4d5f-a004-03c74ee8c228)

There are **126 rules having support of 2% or more and lift more than 1**.  
All the items in these rules have a positive correlation with each other, indicating if the sales of one goes up, the sales of the other goes up as well and vice versa.
