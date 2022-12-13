# Collaborative Document. Day 4, May 20th
2021-05-17-swc-R-nlesc

Welcome to The Workshop Collaborative Document


This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

All content is publicly available under the Creative Commons Attribution License

https://creativecommons.org/licenses/by/4.0/

 ----------------------------------------------------------------------------

This is the Document for today: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-04)

Collaborative Document day 1: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-01)

Collaborative Document day 2: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-02)

Collaborative Document day 3: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-03)

Collaborative Document day 4: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-04)



## 👮Code of Conduct

* Participants are expected to follow those guidelines:
* Use welcoming and inclusive language
* Be respectful of different viewpoints and experiences
* Gracefully accept constructive criticism
* Focus on what is best for the community
* Show courtesy and respect towards other community members


## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: https://creativecommons.org/licenses/by/4.0/



## 🙋Getting help
to ask a question, type `/hand` in the chat window

to get help, type `/help` in the chat window

you can ask questions in the document or chat window and helpers will try to help you


## 🖥 Workshop website

[link](https://escience-academy.github.io/2021-05-17-swc-R-nlesc/)

🛠 Setup
[link](https://escience-academy.github.io/2021-05-17-swc-R-nlesc/#setup)

Download files
[link](https://escience-academy.github.io/2021-05-17-swc-R-nlesc/#setup)

Post-workshop survey
[link](https://carpentries.typeform.com/to/UgVdRQ?slug=2021-05-17-swc-R-nlesc)

Sign up for workshop invitations
[link](https://esciencecenter.us8.list-manage.com/subscribe/post?u=a0a563ca342f1949246a9f92f&id=31bfc2303d)

## 👩‍🏫👩‍💻🎓 Instructors

Pablo Rodríguez-Sánchez, Alessio Sclocco, Barbara Vreede


## 🧑‍🙋 Helpers

Lieke de Boer


## Question

## 🗓️ Agenda

Day 4, May 20th
|        |                                                  |
|:-------|:-------------------------------------------------|
| 09:00  | Graphics with ggplot2                            |
| 10:00  | Functions explained                              |
| 10:15  | Coffee break                                     |
| 10:30  | Functions explained (continued)                  |
| 11:30  | Coffee break                                     |
| 11:45  | Producing reports with knitr                     |
| 12:30  | Wrap-up and post-workshop                         |
| 12:45  | Survey                                           |
| 13:00  | END                                              |


## Feedback

### Tips :thumbsdown: 
- None!

### Tops :thumbsup: 
- Very clear workshop again today, easy to follow and good examples. I also liked the plot discussion in the break-out room
- Cat from Barbara behind the webcam every day ;) 
- The R markdown option is very useful and powerful, which I did not know before. 

## 🧠 Collaborative Notes

### Exercises

**Exercise 1**

It could be interesting to explore if there is a relationship between the gdp per capita and the life expectancy. How would you make a scatter plot where the horizontal position of the point is the gdp per capita, the vertical position the life expectancy and the color is the continent?

**Exercise 2**

The relationship between kelvin and celsius is: T_kelvin = T_celsius + 273.15. Write a function that converts **from** kelvin **to** celsius.

**Exercise 3**

Write a function that converts from fahrenheit to celsius.


### Command history

#### Prepare our work: loading libraries
```r=
library(gapminder)
library(ggplot2)

```
If you run into trouble with loading the libraries:

```r=
install.packages("name_of_library")
```
Click on the save-button to save the script to a file.

Check the content of the data:
```r=
head(gapminder)
```

#### Plotting data

- Ctrl + enter will execute lines in a script.
- GGplot stands for "grammar of graphics".
    - Graphics have separate elements:
        - the data (`data` argument)
        - the mapping/aesthetics (`mapping` argument, with `aes()` function)
        - the geometry (a separate function: like `geom_point()`)

Plot how gdp changed in time.

```r=
ggplot(data = gapminder,
       mapping = aes(x = year, y = lifeExp)) +
    geom_point()
```
Clear the plot window with the broom in the bottom right panel (optional).

Improve the plot with colors:
```r=
ggplot(data = gapminder,
       mapping = aes(x = year, y = lifeExp, color = continent)) +
    geom_point()
```

Try to use lines instead of points:
```r=
ggplot(data = gapminder,
       mapping = aes(x = year, y = lifeExp, color = continent)) +
    geom_line()
```
OMG what is happening!
- R is linking points in the same year
- Only the last point in the same year will connect to the next year

We are now grouping the lines by country:
```r=
ggplot(data = gapminder,
       mapping = aes(x = year, y = lifeExp, color = continent, by = country)) +
    geom_line()
```

Can we add points to this graph?
```r=
ggplot(data = gapminder,
       mapping = aes(x = year, y = lifeExp, color = continent, by = country)) +
    geom_line() +
    geom_point()
```
If you would want your colors to be independent of the underlying data:
```r=
ggplot(data = gapminder,
       mapping = aes(x = year, y = lifeExp, color = continent, by = country)) +
    geom_line() +
    geom_point(color = "black")
```
This way, the point shapes will be unique to each continent.
```r=
ggplot(data = gapminder,
       mapping = aes(x = year, y = lifeExp, color = continent, by = country)) +
    geom_line() +
    geom_point(mapping = aes(shape = continent))
```

Exercise:
How would you make a scatter plot where the horizontal position of the point is the gdp per capita, the vertical position the life expectancy and the color is the continent?
```r=
ggplot(data = gapminder,
       mapping = aes(x = gdpPercap, y = lifeExp, color = continent)) +
  geom_point()
```
**TIP**: be kind to yourself and use informative names for your table headers, variables, etc... 

If you use pipes, you can use autocomplete for column names!
```r=
library(magrittr)

gapminder %>%
  ggplot(mapping = aes(x = gdpPercap, y = lifeExp, color = continent)) +
    geom_point()
```

To make the plot clearer, you can change the transparency of the dots, to see from the density of the colors how many points are there.

```r=
ggplot(data = gapminder,
       mapping = aes(x = gdpPercap, y = lifeExp, color = continent)) +
  geom_point(alpha = 0.5)
```
Change the scale on the x axis to clear up the dense points on the left:
```r=
ggplot(data = gapminder,
       mapping = aes(x = gdpPercap, y = lifeExp, color = continent)) +
  geom_point(alpha = 0.5) +
  scale_x_log10()
```

Make some statistics with ggplot: a linear regression, for example.
```r=
ggplot(data = gapminder,
       mapping = aes(x = gdpPercap, y = lifeExp, color = continent)) +
  geom_point(alpha = 0.5) +
  scale_x_log10() +
  geom_smooth(method = "lm", size = 1.5)
```

Adjust the labels to increase the readability of the plot:
```r=
ggplot(data = gapminder,
       mapping = aes(x = gdpPercap, y = lifeExp, color = continent)) +
  geom_point(alpha = 0.5) +
  scale_x_log10() +
  geom_smooth(method = "lm", size = 1.5) +
  labs(x = "GDP per capita (in million dollars)",
       y = "Life expectancy (in years)")
```

Just for experimentation: apply the regression line to all the points, but keep the colors: 
```r=
ggplot(data = gapminder,
       mapping = aes(x = gdpPercap, y = lifeExp)) +
  geom_point(alpha = 0.5, mapping = aes(color = continent)) +
  scale_x_log10() +
  geom_smooth(method = "lm", size = 1.5) +
  labs(x = "GDP per capita (in million dollars)",
       y = "Life expectancy (in years)")
```

#### Saving plots
Save the plot: use the export button (bottom right panel, where you see the plots)

```r=
p <- ggplot(data = gapminder,
       mapping = aes(x = gdpPercap, y = lifeExp, color = continent)) +
  geom_point(alpha = 0.5) +
  scale_x_log10() +
  geom_smooth(method = "lm", size = 1.5) +
  labs(x = "GDP per capita (in million dollars)",
       y = "Life expectancy (in years)")
       
ggsave(filename = "plot.png", plot = p, width = 12, height = 10, dpi = 300, units = "cm")
```

#### Functions

Functions in computer programming are the same as functions you learned in school:
Something that takes `x` and turns it into something else, like `y`.

Functions can be seen as a machine: it takes something --- like a car --- and add the wheels.

Make a new script called `functions.R`.

Imagine you are working with a British university, and the temperatures from an observatory that you get are in Fahrenheit. You need them in Kelvin. Lets make a function to make that transformation.

```r=
fahr_to_kelvin <- function(t_fahr) {
  t_kelvin <- 5/9 * (t_fahr-32) + 273.15
  return(t_kelvin) # not strictly necessary to have this return statement!
}
```
After running this, it appears in our environment (top right frame). Now we can use it.
```r=
fahr_to_kelvin(32)
fahr_to_kelvin(0)
fahr_to_kelvin(c(1,2,3,4,5))
```

There are no comments with this function! Let's document the function.
You can use an ROxygen skleton through Code > Insert roxygen skeleton
```r=
#' Fahrenheit to Kelvin
#'
#' Converts temperatures in Fahrenheit to temperatures in Kelvin 
#'
#' #param t_fahr The temperature in Fahrenheit
#'
#' @return The temperature in Kelvin
fahr_to_kelvin <- function(t_fahr) {
  t_kelvin <- 5/9 * (t_fahr-32) + 273.15
  return(t_kelvin)
}
```

**Exercise 2**

The relationship between kelvin and celsius is: T_kelvin = T_celsius + 273.15. Write a function that converts **from** kelvin **to** celsius.
```r=
#' Kelvin to Celsius
#'
#' Converts temperatures in Kelvin to temperatures in Celsius 
#'
#' #param t_kelvin The temperature in Kelvin
#'
#' @return The temperature in Celsius
kelvin_to_celsius <- function(t_kelvin) {
  t_celsius <- t_kelvin - 273.15
  return(t_celsius)
}
```

Running the function
```r=
kelvin_to_celsius(0)
```

Making the function robust, by ensuring the input is correct.

```r=
#' Kelvin to Celsius
#'
#' Converts temperatures in Kelvin to temperatures in Celsius 
#'
#' #param t_kelvin The temperature in Kelvin
#'
#' @return The temperature in Celsius
kelvin_to_celsius <- function(t_kelvin) {
  stopifnot(t_kelvin >= 0)
  t_celsius <- t_kelvin - 273.15
  return(t_celsius)
}
```

**Exercise 3**

Write a function that converts from fahrenheit to celsius.
```r=
#' Fahrenheit to Celsius
#'
#' Converts temperatures in Fahrenheit to temperatures in Celsius 
#'
#' #param t_fahr The temperature in Fahrenheit
#'
#' @return The temperature in Celsius
fahr_to_celsius <- function(t_fahr) {
  t_kelvin <- fahr_to_kelvin(t_fahr)
  t_celsius <- kelvin_to_celsius(tkelvin)
  return(t_celsius)
}
```
Or putting everything in a single line:
```r=
fahr_to_celsius <- function(t_fahr) {
  t_celsius <- kelvin_to_celsius(fahr_to_kelvin(t_fahr))
  return(t_celsius)
}
```
That same function, but now with pipes
```r=
library(magrittr)

fahr_to_celsius <- function(t_fahr) {
  t_fahr %>%
    fahr_to_kelvin() %>%
    kelvin_to_celsius() %>%
    return()
}
```

Essentially, it does this, but using existing machinery:
```r=
fahr_to_celsius <- function(t_fahr) {
  t_kelvin <- 5/9 * (t_fahr-32) + 273.15
  stopifnot(t_kelvin >= 0)
  t_celsius <- t_kelvin - 273.15
  return(t_celsius)
}
```

Rule of thumb:
Whenever you are copy-pasting part of your script, you can turn it into a function!

Let's make a function specifically for the dataset `gapminder`
```r=
library(gapminder)
calculate_gdp <- function(data) {
  gdp <- data$pop * data$gdpPercap
  return(gdp)
}

calculate_gdp(gapminder)

# add the column:
cbind(gapminder, calculate_gdp(gapminder))
```

Apply this only to a single year, with 2002 being the default:
```r=
library(gapminder)
calculate_gdp <- function(data, year = 2002) {
  data <- data[data$year == year, ]
  gdp <- data$pop * data$gdpPercap
  return(gdp)
}
```

If you run it now without a year, it will by default use 2002
```r=
calculate_gdp(gapminder)
```

But this function can also be used for other years, which can be specified:
```r=
calculate_gdp(gapminder, 1980)
```

If you have a file full of functions, and you want to run that file without opening it:
```r=
source("myfile.R")
```

### R Markdown
"The best part of R!" - pablo

File > New file > R markdown

Advice is to leave it to HTML (and there are more options, and you can edit it later!).

Chunks of code will look like this:
```{r}

```
And outside you can use Markdown (like in this here collaborative doc!)

The extension is .Rmd, and it starts like this:


---
title: "Your title"
author: "Your name"
date: "3/20/2021"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
## R markdown

Here is an example of a chunk:
```{r cars}
summary(cars)
```

## Including Plots

You can also embed plots, for example:

```{r pressure, echo=FALSE}
plot(pressure)
```

By pressing the 'Knit' button, it will generate a rendered HTML (in a separate window), that includes both R code and Markdown text.

If you change the name of the output, for instance: pdf_document instead of html_document, it will make a pdf instead.

#### But Pablo, is this not overkill?
It is one step more complicated, but the potential is huge. Your document can be used to share your work, and include any explanations, ideas, processes, etc. All the details (and the formatting!) can be included.

And someone else can execute the entire work with one click!

Every time you knit the document, it knits from scratch and runs all the chunks. You can prevent this with `cache = TRUE` in the `{r}` field:

```{r cache=TRUE}
# here would be a long calculation. It will not be executed when you press 'knit'
```

If you want to include the code in the resulting document, the default of a chunk will do that.

But if you want the code *not* to be there in the document, use this:

```{r echo=FALSE}
# this code will not show up in the rendered document
```
It is recommended to name your chunks, like so:
```{r chunk_name, echo=FALSE}
# here is code pertaining to the chunk name
```

Headers in the markdown will not only show up in your rendered document, but also are helpful with navigation:

## Here is a sub header

There are two types of equations:

- Inline
- Blocks

Inline equations are written inside dollar signs: $a^2 + b^2 = c^2$. Block equations are written like this:

$$
a^2 + b^2 = c^2
e^{i \theta} = \cos \theta + i \sin \theta
$$

You can also use R code inline: `r mean(c(2,4,6,902))` for instance.


By changing the output to word_document, you can knit to a word document!
You can use version control like Git on an R markdown document really well, as it is a plain text document. Git will also work on word documents, but only in the sense that it will save different versions. The difference between versions will not be informative (word is a binary file, not plain text).



## Internal links
- [Check in / question table](#Question)
- [Command history](#Command-history)
- [Exercises](#Exercises)
- [Feedback](#Feedback)


## 📚 Resources
- [eScience Center Blog](https://blog.esciencecenter.nl/)
- [List of upcoming eScience Center courses](https://escience-academy.github.io/)
- Book: [R for Data Science](https://r4ds.had.co.nz/)
- [R cheat sheets](https://www.rstudio.com/resources/cheatsheets/) provided by the R community and RStudio, describing common procedures and packages. 
    - [Base R](http://github.com/rstudio/cheatsheets/raw/master/base-r.pdf)
    - [R Markdown](https://github.com/rstudio/cheatsheets/raw/master/rmarkdown-2.0.pdf)
    - [Data Import](https://github.com/rstudio/cheatsheets/raw/master/data-import.pdf)
    - [Data Transformation with dplyr](https://github.com/rstudio/cheatsheets/raw/master/data-transformation.pdf)
    - [Data Visualization with ggplot2](https://github.com/rstudio/cheatsheets/raw/master/data-visualization-2.1.pdf)
- [Tidy Data original paper](https://vita.had.co.nz/papers/tidy-data.html)
- [eScience Center workshop invitations sign-up](Sign up for workshop invitations
[link](https://esciencecenter.us8.list-manage.com/subscribe/post?u=a0a563ca342f1949246a9f92f&id=31bfc2303d)
- [Future workshops](escience-academy.github.io)
- [Integrating Zotero in R Markdown](https://christopherjunk.netlify.app/blog/2019/02/25/zotero-rmarkdown/)
- [WORCS package](https://cjvanlissa.github.io/worcs/index.html): a Workflow for Open Reproducible Code in Science

A graphical summary of dplyr:
![](http://perso.ens-lyon.fr/lise.vaudor/Rfigures/dplyr/dplyr_schema.png)








```r=
rough_year_df <- data %>%
    mutate(rough_year = round(data$year/10000)) %>%
    group_by(species, rough_year)
    
unique()
```

