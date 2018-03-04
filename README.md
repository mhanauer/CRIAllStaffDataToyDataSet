---
title: "Test1"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Create data for ty
```{r}
id = 1:10000
genderSamp = c("Male", "Female", "Other_Identity")
ethSamp = c("White", "African_American", "Asian", "Hispanic", "Other_Ethnic_Identity")
SESSamp = c("Very_Low", "Low", "Middle", "High")
set.seed(12345)
preScore = abs(rnorm(10000, 50, 10))
postScore = abs(rnorm(10000, 60, 10))
dat = data.frame(id, Gender = sample(genderSamp, 10000, replace = TRUE, prob = c(.40, .30, .30)), Ethnicity = sample(ethSamp, 10000, replace = TRUE, prob = c(rep(.2, 5))), SES = sample(SESSamp, 10000, replace = TRUE, prob = c(rep(.25, 4))), preScore = round(preScore, 0), postScore = round(postScore, 0)); dat

write.csv(dat, "dat.csv", row.names = FALSE)
```

