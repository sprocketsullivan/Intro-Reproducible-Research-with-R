---
title: Homework Session 2
description: no description.
---

## Recap of last Session

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: 81c685b3b3
```

100 men and 100 women agreed to have their brain volume as well as their body weight measured. We put the resulting data into variable `my.data` in your R workspace. `my.data` is of type `data frame` (see Chapter 5 of course "Introduction to R").

`@instructions`
- Use [`summary()`](https://www.rdocumentation.org/packages/base/versions/3.4.3/topics/summary) on `my.data` to have a look at its structure.
- Calculate the mean ($\mu$) of brain volume. brain volume is stored in field `brain` of `my.data`.
- Use [`aggregate()`](https://www.rdocumentation.org/packages/stats/versions/3.4.3/topics/aggregate) to calculate the mean for each gender.
- Do the same for the standard deviation ($\sigma$).


`@hint`
Have a look at the plot. Which color does the point with the lowest rating have?

`@pre_exercise_code`

```{r}
library(dplyr)
my.data<-data.frame(brain=rnorm(100),gender=c("male","female"))
```

`@sample_code`

```{r}
# summary(my.data)


#average brain


#aggregate over gender and calculate the brain volume


#aggregate over gender and calculate the standard deviation

```

`@solution`

```{r}
# summary(my.data)
summary(my.data)

#average brain
mean(my.data$brain)

#aggregate over gender and calculate the brain volume
aggregate(my.data$brain,list(my.data$gender),mean)

#aggregate over gender and calculate the standard deviation
aggregate(my.data$brain,list(my.data$gender),sd)

```

`@sct`

```{r}
success_msg("Good work!")
```

