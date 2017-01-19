---
title: Filtering rows
description: Description

--- type:VideoExercise lang:r xp:50 skills:1 key:99389a38c5
## Filter rows with WHERE

* WHERE
* Filtering numeric vs. text values
* Basic comparison operators: =, <>, <, <=, >, >=
* Multiple conditions with AND, OR

*** =video_link
//player.vimeo.com/video/154783078

*** =video_hls
//videos.datacamp.com/transcoded/000_placeholders/v1/hls-temp.master.m3u8

--- type:NormalExercise lang:r xp:100 skills:1 key:d8a10b6acf
## Filter for a single condition

Practice filtering for numeric and text values. Start with = and <>, then move to inequalities

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```

--- type:NormalExercise lang:r xp:100 skills:1 key:da1f20241a
## Filter for multiple conditions

Same as above, but incorporate AND, OR. Recall something from chapter 1, like DISTINCT or aggregate functions? Do at least one >= AND <= for comparison to BETWEEN in later exercise

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```

--- type:VideoExercise lang:r xp:50 skills:1 key:b48f90b55e
## More advanced filtering

* BETWEEN (compare to >= AND <= )
* IN (compare to = AND = )
* IS NULL, IS NOT NULL

*** =video_link
//player.vimeo.com/video/154783078

*** =video_hls
//videos.datacamp.com/transcoded/000_placeholders/v1/hls-temp.master.m3u8

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:d90a7dd18e
## Look familiar?

Give students a SELECT statement using BETWEEN and have them select an equivalent statement using >= AND <=

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}

```

--- type:NormalExercise lang:r xp:100 skills:1 key:bab3080fee
## Stuck somewhere IN BETWEEN

Practice filtering with BETWEEN and IN

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```

--- type:NormalExercise lang:r xp:100 skills:1 key:858b8669c5
## Manage missingness

Practice with IN NULL and IS NOT NULL. Combine with COUNT, DISTINCT, and/or other concepts from earlier

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```

--- type:VideoExercise lang:r xp:50 skills:1 key:532f0aaa6d
## Search for patterns with LIKE

* LIKE
* Wildcards: %, _, [charlist], [!charlist]

*** =video_link
//player.vimeo.com/video/154783078

*** =video_hls
//videos.datacamp.com/transcoded/000_placeholders/v1/hls-temp.master.m3u8

--- type:NormalExercise lang:r xp:100 skills:1 key:6623416f5f
## LIKE it or NOT

Practice with some simple pattern matching using LIKE with % and _. Then combine with NOT.

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```

--- type:NormalExercise lang:r xp:100 skills:1 key:643c255c48
## Pattern matching mania

Practice with LIKE some more, using more advanced wildcards: sets and ranges of characters. Use negation (!) as well. Finish with embedded MCE for interpretation

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```

--- type:VideoExercise lang:r xp:50 skills:1 key:9428c95ce6
## Simple subqueries

Introduce subqueries as a convenient way to filter on values that aren't readily available in the table of interest. These values may be the result of a second filtering operation on the same table, or they may come from a different table entirely. Use as teaser for future course covering joins. We will only cover very simple examples here

*** =video_link
//player.vimeo.com/video/154783078

*** =video_hls
//videos.datacamp.com/transcoded/000_placeholders/v1/hls-temp.master.m3u8

--- type:NormalExercise lang:r xp:100 skills:1 key:ff4114109d
## Single table subqueries

Perform a couple of subqueries using information from only one table. Finish with embedded MCE to drill home motivation

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```

--- type:NormalExercise lang:r xp:100 skills:1 key:8b8b4b735f
## Two table subqueries

Perform some two table subqueries (i.e. use values from another table to filter this table). Finish again with an MCE to interpret the results

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```