# Import and export data to CSV

Using R you can import your data from external data sources. One of the most popular scenario is that you want to analyze data from `.csv` file. I will describe this use case below.

## Import data from file

To import data from `.csv` file to R use function `read.csv`

Example use if you want to import file named `file_to_import.csv` from your _working directory_ and save data in data frame `df`:

```r
df <- read.csv('file_to_import.csv')
```

Sometimes you need some extra options like header or separator.

If you don't want to import first line of your file, use `header = FALSE` option.

Also if you have column separator other than comma `,` use `sep=';'` option - you can declare your separator in this place.

Example code with options:

```r
df <- read.csv('file_to_import.csv', header = FALSE, sep=';')
```

### Where is my working directory?

To check working directory type in R console:

```r
getwd()
```

```r
[1] "/Users/michal"
```

## Export data

After conducted analysis you may want to save results in file to use it in other tools. To do this you need `write.csv` function.

If you have data in data frame called `ga.data` you can use this code:

```r
write.csv(gadata, file = "exported_data.csv")
```

As a result R will export data to `.csv` file. You can open it in every text editor or spreadsheet \(i.e. Microsoft Excel\). Other use case is upload data as **custom dimension** or **campaign cost data** to Google Analytics.

### Where I can find saved file?

Your `.csv` file is in your _working directory_.

