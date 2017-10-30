
### **Always be curious and skeptical when you're taking a look at data!**

EDA - Exploratory Data Analysis 探索性数据分析

    udacious <- c( "Chris Saden", "Lauren Castellano",
              "Sarah Spikes","Dean Eckles",
              "Andy Brown", "Moira Burke",
              "Kunal Chawla")

'<-' symbol is the assignment operator in R, similar to the
equal sign '=' in other programming languages.

The c() is a generic function that combines arguments, in this case the names of people, to form a vector.  
  
A 'vector' is one of the data types in R. Vectors must contain the same type of data,that is the entries   
must all be of the same type: character (most programmers call these strings),logical (TRUE or FALSE), or numeric.

You can add values to a vector:

        >numbers <- c(1:10)
        > numbers
        [1]  1  2  3  4  5  6  7  8  9 10
        > numbers <- c(numbers, 11:20)
        > numbers
        [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20

        >udacious <- c( "Chris Saden", "Lauren Castellano",
                  "Sarah Spikes","Dean Eckles",
                  "Andy Brown", "Moira Burke",
                  "Kunal Chawla", "wwj")
        > mystery = nchar(udacious)
        > mystery
        [1] 11 17 12 11 10 11 12  3

Mystery is a vector that contains the number of characters for each of the names in udacious, including your name.

        > mystery == 11
        [1]  TRUE FALSE FALSE  TRUE FALSE  TRUE FALSE FALSE
        > udacious[mystery == 11]
        [1] "Chris Saden" "Dean Eckles" "Moira Burke"

Run this next command to load the mtcars data.

        data(mtcars)

names(mtcars) should output all the variable names in the data set.

**?mtcars**　　You can type a '?' before any command or a data set to learn more about it.   
The details and documentation will appear in the 'Help' tab.

str(mtcars), gives us the structure of the data frame. It lists the variable names,  
the type of each variable (all of these variables are numerics) and some values for each variable.  
R uses 1 to start indexing (AND NOT ZERO BASED INDEXING as is true of many other programming languages.)

**?row.names**  　Read the documentation for row.names if you're want to know more.  

**row.names**  　Run this code to see the current row names in the data frame.

**row.names(mtcars) <- c(1:32)**　　Run this code to change the row names of the cars to numbers.

**head(mtcars)**　　The head() function prints out the first six rows of a data frame by default. Run the code below to see.

**mtcars$mpg**

We can access an individual variable (or column) from the data frame using the '$' sign.

**mean(mtcars$mpg)**

Caculate the average of the mpg.

**getwd()**   查看当前工作目录

**setwd('~/Downloads')**   更改当前工作目录

**list.files()**    查看当前目录的文件

**data <- read.csv('stateData.csv')** 读取CSV文件

**pf <- read.delim('pseudo_facebook.tsv')**

**read.delim()** 函数默认使用制表符作为值之间的分隔符，并使用句点作为十进制字符。

**subset(data, state.region == 1)**  创建state.region = 1 的子集

[R快速入门](https://www.statmethods.net/)

[R COOK BOOK](http://www.cookbook-r.com/)

[R-Bloggers](https://www.r-bloggers.com/)

[StackOverflow 上的 R 语言简介](https://stackoverflow.com/tags/r/info)

[StackOverflow R 常见问题解答](https://stackoverflow.com/questions/tagged/r-faq%20)

[Google R 风格指南](https://google.github.io/styleguide/Rguide.xml)
