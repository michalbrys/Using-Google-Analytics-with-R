# Import and export data to CSV

In R you can import your data from external data sources. One of the most popular scenario is when you want to analyze data from a `.csv` file. I will describe this use case below.

## Import data from a file

To import data from a `.csv` file to R use `read_csv` from `readr` which is a part of `tidyverse`.

For example, if you want to import data from a file named `file_to_import.csv` in your _working directory_ and save it in a data frame named `df`, use:

```r
library(tidyverse)
df <- read_csv('file_to_import.csv')
```

Sometimes you need some extra options like header or separator.

If you don't want to import first line of your file, use `col_names = FALSE` option.

Also if you have column separator other than comma `,` use `delim';'` option - you can declare your separator in this place.

Example of the code with options mentioned above:

```r
df <- read_csv('file_to_import.csv', col_names = FALSE, delim = ';')
```

### Where is my working directory?

To check the working directory type in the R console:

```r
getwd()
```

```r
[1] "/Users/michal"
```

## Export data

After having conducted the analysis you may want to save the results in a file to use it in some other tools. To do this you need the `write_csv` function.

If you want to save data from a data frame called `ga.data` you can use the following code:

```r
write_csv(file = "exported_data.csv", ga.data)
```

As a result R will export data to the `.csv` file. You can open it in every text editor or spreadsheet (i.e. Microsoft Excel). The other use case is to upload data as `custom dimension` or `campaign cost data` to Google Analytics.

### Where can I find saved file?

Your saved `.csv` file is in your _working directory_.

