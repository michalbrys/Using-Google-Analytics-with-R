# Introduction to R Markdown

You can use markdown using the following examples:

### R Markdown options

```
---
title: "Monthly report"
output: pdf_document
---
```

### Chunks of code

```{r}
```{r}    
# R Code
```r
```

If you don't want to display the code of the chunk in the output file, use `echo = FALSE` option.

    ```{r, echo=FALSE}
    # R Code
    ```

### Basic formatting

#### Headers

```
# Header 1
## Header 2
### Header 3
```

will produce

# Header 1

## Header 2

### Header 3

### Lists

```
* element 1
* element 2
* element 3
```

will produce

* element 1

* element 2

* element 3


```
1. element 1
2. element 2
3. element 3
```

will produce

1. element 1

2. element 2

3. element 3


### Formatting

```
*italic*
**bold**
**_bold+italic_**
```

will produce

_italic_
**bold**
**_bold+italic_**

### More resources

**Full documentation:  **

[www.rstudio.com\/wp-content\/uploads\/2015\/03\/rmarkdown-reference.pdf](http://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf)

**Cheat sheet:**

[www.rstudio.com\/wp-content\/uploads\/2016\/03\/rmarkdown-cheatsheet-2.0.pdf](http://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf)

