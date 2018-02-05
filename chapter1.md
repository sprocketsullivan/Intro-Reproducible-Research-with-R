---
title: Homework Session 2
description: .
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
n<-100
set.seed(123)
my.data<-data.frame(gender=c(rep("male",n),rep("female",n)), brain=c(rnorm(n,1273,100),rnorm(n,1131,100)))
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

---
## Barplot

```yaml
type: NormalExercise
key: a9ff08577c
lang: r
xp: 100
skills: 1
```
We provide dataframe `p.bar.data` that contains the mean and its standard error ($\frac{\sigma}{\sqrt{N}}$) for the brain volume of each gender.

You may want to use [`str()`](https://www.rdocumentation.org/packages/utils/versions/3.4.3/topics/str) or [`summary()`](https://www.rdocumentation.org/packages/base/versions/3.4.3/topics/summary) on `p.bar.data` to have a look at its structure.

`@instructions`
- Use function [`ggplot()`](https://www.rdocumentation.org/packages/ggplot2/versions/2.2.1/topics/ggplot) for data mapping
    - parameter `data` tells `ggplot` where your data is stored.
    - parameter `aes` tells `ggplot` which parts of your data to map to the x-axis and the y-axis, respectively. You plan to plot gender against the respective average brain volume.
- Use [`geom_bar()`](https://www.rdocumentation.org/packages/ggplot2/versions/2.2.1/topics/geom_bar) to do a simple bar blot. Use `stat="identity"` to make the heights of the bars represent values in the data mapped to the y-axis.
- Use [`geom_errorbar()`](https://www.rdocumentation.org/packages/ggplot2/versions/2.2.1/topics/geom_crossbar) to add error bars to the bar plot.


`@hint`
Have a look at the plot. Which color does the point with the lowest rating have?
`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```
