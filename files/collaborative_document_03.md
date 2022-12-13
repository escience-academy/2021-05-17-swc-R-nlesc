# Collaborative Document. Day 3, May 19th
2021-05-17-swc-R-nlesc

Welcome to The Workshop Collaborative Document


This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

All content is publicly available under the Creative Commons Attribution License

https://creativecommons.org/licenses/by/4.0/

 ----------------------------------------------------------------------------

This is the Document for today: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-03)

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

### 🛠 Setup
[link](https://escience-academy.github.io/2021-05-17-swc-R-nlesc/#setup)

#### For today:
- The language [R](https://cran.rstudio.com/)
- The interface [Rstudio](https://www.rstudio.com/products/rstudio/download/#download)


## 👩‍🏫👩‍💻🎓 Instructors

Pablo Rodríguez-Sánchez, Alessio Sclocco, Barbara Vreede


## 🧑‍🙋 Helpers

Lieke de Boer

## 🗓️ Agenda

Day 3, May 19th
|        |                                                  |
|:-------|:-------------------------------------------------|
| 09:00  | Introduction to R and RStudio                    |
| 10:00  | Data structures                                  |
| 10:15  | Coffee break                                     |
| 10:30  | Data structures (Continued)                      |
| 11:00  | Exploring data frames                            |
| 11:30  | Coffee break                                     |
| 11:45  | Data frame manipulation with dplyr               |
| 12:45  | Wrap-up                                          |
| 13:00  | END                                              |

## Feedback

## Tips

* Really informative presentation, with really practical application. I would like it just a little bit more if it was focusing a little bit more in the theory about why we are taking each step in the code.
* Tip: 1. To not delete the commands to fix or change but to copy and paste and start a new one with the new fix.  So that we can track the differencce. 2.  To quickly wrap up the last 3 functions taught before continue to the next.
* Maybe more information about data types in R 
* Would be helpful to link with Git a bit more
* It started on a good speed, but on the hardest part at the end it was too quick
* The 
* I would like to have more information on packages and renv. 
* Some examples were apparently created "on the fly" and then they didn't work. That got me really confused
* Sometimes when you wrote code, executed it you'd scroll down and we couldn't see the code you used. Maybe just make sure the original code is available for a bit longer so we don't have to switch to the collaborative document all the time. 
* I think there was a lot of improvised examples and it became confusing when code had to be debugged on the spot. Sometimes the speaker also switched too quickly from her script to the viewer window to see the data frame. Is there any way to show code and the output separately to avoid switching between script and viewer too quickly frequently?
* The demonstration is a bit fast for people who first time using R. It would be be better to slow down a little bit or add description of the demonstration to the collaborative document. 

## Tops

* I like how we started with base R first and contrasting it to the tidyverse way of wrangling data. It really shows the value of working with the tidyverse. 
* Moving to HackMD instead of the chat window was a good idea
* I liked how comments were added to each line of code to explain what was done.
* I liked it when you encountered issues and we saw the process you went through to overcome the issue. Inevitably we will encounter issues and the process to overcome them is really useful info. 
* I like the additional resources are provided to go through later.
* I like how Barbara explains, it makes things realy clear
* I liked that Barbara explained where are common mistakes done, from her experience. Very useful!
* Very informative workshop, thanks Barbara (love your passion!) and the helpers for the useful information.
* Very  Infomrative, great job! 
* I like the approach of trial and error also by Barbara, a good example of the reality of working in R 

## Response to Tip/Top!
- More info on Renv: [landing page](https://rstudio.github.io/renv/) | [vignette](https://rstudio.github.io/renv/articles/renv.html) | [talk by the creator](https://www.youtube.com/watch?v=yjlEbIDevOs)
  (There is so much more to say about dependencies, but it is an advanced subject, and we are struggling with this too! Renv is an excellent option for R users though, and I encourage you to look into this to make reproducible R code!)
  
- Apologies for the bad preparation of some examples. These courses bring so much inspiration sometimes that I want to try something new, but apparently I have to google things more often that I'd like to admit :) 


## Check in

Suggested symbols:
- yes: :heavy_check_mark:
- no: :red_circle:
- extra option: :star:

Question: 

 
### Best group_by summarize combinations
The maximum life expectancy per country
```
gm %>%
  group_by(country) %>%
  summarize(avg_max_lifeExp = max(lifeExp)) %>%
  view()
```


Take a look at other functions for mass calculations:
```
max()
min()
median()
```

The average population size and life expectancy, per continent and year:
```r=
gm %>%
  group_by(continent, year) %>%
  summarize(avg_pop_size = mean(pop), avg_life_exp = mean(lifeExp)) %>%
  View()
```
global life expectancy and population size per year
```r=
gm %>% 
  group_by(year) %>% 
  summarise(golbal_pop_size = mean(pop), global_life_expectancy = mean(lifeExp)
```

Average GDP and life expectancy per continent per year

```r= 
gm %>% 
  group_by(continent, year) %>%
  summarize(avg_gdp = mean(gdpPercap), avg_life_exp = mean(lifeExp))
```

```r=
  gm %>% 
  group_by(year) %>% 
  summarize(avr_lifeExp = mean(lifeExp))
```

```r=
  gm %>% 
  group_by(continent) %>% 
  summarize(avr_lifeExp = mean(lifeExp))
```

```r=
gm %>%  
   group_by(country, year) %>% 
   summarise(gdpPercap=mean(gdpPercap))
 
 Average gdp for each continent per country 
```

```r=
  gm %>%
  group_by(continent, country) %>%
  summarize(avg_gdp = mean(gdpPercap)) %>%
  View() 
```

```r=
#Life expectancy/year/country
gm %>%
 group_by(country)%>%
  summarise(year, lifeExp)%>%
  View()
```

```r=
gm %>% 
  group_by(continent) %>% 
  summarize (avg_gdp = max(gdpPercap)) %>% 
  View()
```

```r=
gm %>% 
  group_by (country) %>% 
  filter(continent == "Europe") %>% 
  summarize (avg_gdp = max(gdpPercap)) %>% 
  View()
```


## 🧠 Collaborative Notes

### Command history
```r=
1+4
3+5
(56/8)+4
```
 / command + enter executes these lines

```r=
log(10) # when run should return 2.302585
(log(10) +4)/11
"hello world!" # a string that's returned when it's run
```
saving variables

```r=
calc <- (log(10) +4)/11 # is not printed when run, but saved in the calc variable
text <- "hello world!" #string
logic <- T # logical TRUE (do not give it the name of an existing function)

```

testing something

```r=
text == "hello world" #returns FALSE (if text is defined with exclamation point)
text = "hello world" # makes text equal to hello world
text == "hello world" # should now return TRUE

"hello world!" -> text # works similarly to first assignment 

calc > 1 # is calc greater than 1?
calc >= 1 # is calc greater or equal to 1?
calc < 1
calc <= 1 # spaces not necessary but stylistic choice
calc != 1 # is calc unequal to 1? 

#unexpected!
calc =! 1  # R interprets this as, calc is a variable that is not equal to 1 (which means TRUE in this case), so calc equals FALSE
```

other datatypes

```r=
vec <- c(1,2,3,45,87) # a vector of five numbers
vec * 3

vec2 <- c(2,3,4,6,1) # second vector of five numbers
vec * vec2 # multiplies the vectors elementwise

vec1 <- 1:5
vec2 <- 1:3
vec1 * vec2 # what happens? R multiplies the two vectors, but starts repeating the shorter vector for each longer element of the longer vector

```

calcuations

```r=

vec1 <- 1:6
vec2 <- 1:3

mean(vec1)
vec3 <- c(2,4,5,NA)
mean(vec3) # returns NA
mean(vec3, na.rm = TRUE)
?mean # will show you the help page for mean
```

the importance of ```c```

```r=
mean(1,6,3,8,2) # R interprets this as mean of 1
mean(c(1,6,3,8,2)) # this calculates the mean of the entire vector
```

installing packages

```r=
install.packages("gapminder")
library(gapminder) # now the objects in the package are available to you
gapminder # should show you the dataset

install.packages("tidyverse")
library(tidyverse)
```

Shift + command/control + C comments a block of code

create a new project in gapminder
tick the box "Create a git repository" in the project wizard (only visible if git is installed)

Tick new files - click commit, type a commit message (e.g. "First commit"), and commit to your git repository.

## data frames

```r=
cats <- data.frame(
    name = c("Fluffy", "Blacky", "Tahini", "Simba"),
    coat = c("Black", "Black", "Calico", "Red"),
    weight = c(3, 4, 1.5, 6.1),
    likes_sticks = c(T, F, F, T)
)

str() # gives you the structure of the dataframe
head() # first 5 observations
tail() # last 5 observations
names() # column names
summary() # some 
dim()
```

changing types of variables

```r=

cats$coat <- factor(cats$coat)
summary(cats) # gives us a count of each categorical variable after having changed coat to a vector

cats$legs <- factor(c(4,4,4,3))
cats$legs <- as.numeric(cats$legs) 
cats$legs <- factor(c(4,4,4,3))
cats$legs <- as.numeric(as.character(cats$legs)) # does not convert factors to different numbers
```
```NA``` as an entry

```r=
cats$favorite_food <- c("kibble", "fish", "fish", NA) # NA stands for not available (it exists, but we do not know what it is)
cats$favorite_food <- factor(cats$favorite_food)
summary(cats)
levels(cats$favorite_food) #NAs are not a level

```

Adding more information (age and another cat) 

```r=
cats <- cbind(cats, age = c(4,6,2,0))
cats <- rbind(cats, c("Toby", "white", 5, TRUE, 4, "fish", 5)) # error because white is not a level of coat

levels(cats$coat) <- c(levels(cats$coat), "white") # add this level to the factors
```
## selecting data

```r=

cats[c(1,2),] #first and second row, all columns
cats[c(1,2),2] # first and second row, second column

cats$likes_sticks==TRUE # indicates which cats like sticks

cats[cats$likes_sticks==TRUE,]

```

## gapminder data

```r=

library(gapminder)
library(tidyverse)

df <- gapminder 
write_delim(df, file = 'gapminder.csv',
            delim = ",") # creates a new file: gapminder.csv
            
```

## import text data 
(via import data file, import text with readr)

copy the code needed to import the datafile (shown in the bottom right)

```r=
gm <- read_csv("gapminder.csv")

select(gm, country, continent) # tidyverse tibble selected columns
gm[c(1,2)] #base selected columns

filter(gm, continent == "Asia") # select only the Asia rows

# %>%

gm %>%
    select(country, continent) %>%
    filter(continent == "Asia")
    
gm %>% 
    filter(pop>10000000) %>%
    select(country, continent) %>%
    count(country) # counts the number of rows
    
gm %>%
    select(country, continent) %>%
    unique() %>% 
    count(continent) #unique combinations of country and continent
    
```
## Tidyverse: dplyr 

```group_by``` function

```gm``` stays the same as source dataframe

```r=

gm %>%
    group_by(country) %>%
    summarize(avg_pop_size = mean(pop))
    
gm %>%
    group_by(continent, year) %>%
    summarize(avg_pop_size = mean(pop)) %>%
    View() # display the average population size for each continent

gm %>%
    group_by(continent, year) %>%
    summarize(avg_life_exp = mean(lifeExp)) %>%
    View() # display the average life expectancy for each continent per year

gm %>%
  group_by(continent, year) %>%
  summarize(highest_gdp = max(gdpPercap)) %>%
  View() #moved this one to above :) 

# try out grouping by different variables and summarizing this data!!

```

```mutate``` function

```r=
gm %>% 
    mutate(
        pop_in_millions = round(pop/1000000, 0)
    ) %>%
    View() # create a new column with population in millions
    
gm_extra <- gm %>%
    mutate(
        pop_in_millions = round(pop/1000000, 0)
        ) # save in other dataframe
        
gm_extra <- gm_extra %>%
    mutate(
        country_type = 
            case_when(
                pop_in_millions > 50 ~ "large",
                pop_in_million > 10 ~ "medium",
                1 ~ "small") # adds a column "country_type", with these new categories
        )
    )
       
gm_extra <- gm_extra %>%
  mutate(
    country_type =
      case_when(
        pop_in_millions > 50 ~ "large",
        pop_in_millions > 10 ~ "medium",
        TRUE ~ "small"
      )
  )

write_delim(gm_extra, "gapminder_extra.csv", delim=",") # save the new data in a separate csv. 

# you can now try selecting based on different variables, different countries or population sizes. Then you can do extra operations based on this information.

```


### Other notes
[Rtools](https://cran.r-project.org/bin/windows/Rtools/)



## Internal links
- [Checkin](#Check-in)
- [Command history](#Command-history)
- [Notes](#Other-notes)


## 📚 Resources
- [Cheat sheet base R](http://github.com/rstudio/cheatsheets/raw/master/base-r.pdf)
- [Cheat sheet Rmarkdown](https://github.com/rstudio/cheatsheets/raw/master/rmarkdown-2.0.pdf)
- [Cheat sheet dplyr](https://github.com/rstudio/cheatsheets/raw/master/data-transformation.pdf)
- [Book: R for Data Science](https://r4ds.had.co.nz/)
- [Tidy Data original paper](https://vita.had.co.nz/papers/tidy-data.html)

A graphical summary of dplyr:
![](http://perso.ens-lyon.fr/lise.vaudor/Rfigures/dplyr/dplyr_schema.png)