# About R

## What is R?

*R is a programming language and software environment for statistical computing and graphics supported by the R Foundation for Statistical Computing. The R language is widely used among statisticians and data miners for developing statistical software and data analysis. Polls, surveys of data miners, and studies of scholarly literature databases show that R's popularity has increased substantially in recent years*. [Wikipedia](https://en.wikipedia.org/wiki/R_programming_language)

## Pros and cons

**R language** is now the fastest growing statistic analysis language. 

The major **advantages** of R:

- **Free**. 
- Offers a lot of **libraries** for different statistical computations. [Actual list of packages](https://cran.r-project.org/web/packages/)
- A lot of **educational materials** (tutorials, MOOCs, blogs) available free in the Internet.
- Has big **community support**.
- Ready to run in different **platforms** (Windows, Mac, Unix). Version for server installation is also available.
- **Fast** because of in-memory computations.

**Disadvantages**? 

- R is **not out-of-the-box solution with GUI** for all analytical problems. You need to write a chunk of code to get the result. It sometimes can be barer for non-technical people to start with. But I hope if you read this book is not problem for you :)
- The advantage of **in-memory computations is sometimes a trap**. In standard installation you can only process data set which fits to RAM memory in your machine. If you have really big data to process - think about other solution like Hadoop (MapReduce) or Apache Spark. If you feel comfortable with R you can run your script on other platforms (reading from HDFS or using SparkR). It is more advanced topic for other book ;)
