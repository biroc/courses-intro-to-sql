---
title: Filtering Rows
description: >-
  This chapter builds on the first by teaching you not only how to select and
  summarize columns of interest, but to filter tables for records satisfying
  some criteria of interest. You'll learn how to use basic comparison operators,
  combine multiple criteria, match patterns in text, and much more.

--- type:TabExercise lang:sql xp:100 skills:1 key:b90db25f33
## Simple Filtering of Text
Some basic filtering examples on text

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: 8ad94adbc4

*** =instructions1
Get all French language films.
*** =solution1
```
SELECT *
FROM films
WHERE language = 'French';
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type2: NormalExercise
*** =key2: d632aa4ca2

*** =instructions2
Get the name of the person born on November 11th, 1974.
*** =solution2
```
SELECT name, birthdate
FROM people
WHERE birthdate = '1974-11-11';
```
*** =sct2
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='name', match='any')
Ex().test_column(name='birthdate', match='any')
Ex().has_equal_ast()
```

*** =type3: NormalExercise
*** =key3: d0ef3597af

*** =instructions3
Get the number of Hindi movies.
*** =solution3
```
SELECT COUNT(*)
FROM films
WHERE language = 'Hindi';
```
*** =sct3
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type4: NormalExercise
*** =key4: 7ac32e3dab

*** =instructions4
Get all movies with an R certification.
*** =solution4
```
SELECT *
FROM films
WHERE certification = 'R';
```
*** =sct4
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

--- type:TabExercise lang:sql xp:100 skills:1 key:b90db25f34
## Simple Filtering of Numeric values
Some basic filtering examples on numeric values.

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: 43ab64543d

*** =instructions1
Get all films released in 2016.
*** =solution1
```
SELECT *
FROM films
WHERE release_year = 2016;
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type2: NormalExercise
*** =key2: 7ffac9fec6

*** =instructions2
Get all films released in 2016.
*** =solution2
```
SELECT *
FROM films
WHERE release_year = 2016;
```
*** =sct2
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type3: NormalExercise
*** =key3: 11448daf0b

*** =instructions3
Get the number of films released before 2000.
*** =solution3
```
SELECT COUNT(*)
FROM films
WHERE release_year < 2000;
```
*** =sct3
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type4: NormalExercise
*** =key4: 0f40595c87

*** =instructions4
Get the title and release year of films released since 2000.
*** =solution4
```
SELECT title, release_year
FROM films
WHERE release_year > 2000;
```
*** =sct4
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='title', match='any')
Ex().test_column(name='release_year', match='any')
Ex().has_equal_ast()
```

--- type:TabExercise lang:sql xp:100 skills:1 key:5bda32d7c8
## WHERE AND
Simple exercises combining WHERE with AND clauses

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: 2e6febb3c0

*** =instructions1
Get all Spanish films released before 2000.
*** =solution1
```
SELECT title, release_year
FROM films
WHERE release_year < 2000
AND language = 'Spanish';
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='title', match='any')
Ex().test_column(name='release_year', match='any')
Ex().has_equal_ast()
```

*** =type2: NormalExercise
*** =key2: 4e2b2e035b

*** =instructions2
Get the all Spanish films released since 2000.
*** =solution2
```
SELECT *
FROM films
WHERE release_year > 2000
AND language = 'Spanish';
```
*** =sct2
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type3: NormalExercise
*** =key3: c3c8e3925e

*** =instructions3
Get average duration for films released in France in 1992.
*** =solution3
```
SELECT AVG(duration)
FROM films
WHERE release_year = 1992
AND country = 'France';
```
*** =sct3
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

--- type:TabExercise lang:sql xp:100 skills:1 key:ecc1838fc7
## WHERE AND, OR
Simple exercises combining WHERE, AND and OR clauses.

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: 5f661e6975

*** =instructions1
Get films released in 1990 or released in 2000 in English or Spanish.
*** =solution1
```
SELECT title, release_year
FROM films
WHERE release_year = 1990 OR release_year = 2000
AND language = 'French' OR language = 'Spanish';
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type2: NormalExercise
*** =key2: a57a275ff4

*** =instructions2
Get films released since 2000 that are in French or Spanish, and made more than $20m.
*** =solution2
```
SELECT *
FROM films
WHERE release_year > 2000
AND language = 'French' OR language = 'Spanish'
AND gross > 20000000;
```
*** =sct2
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type3: NormalExercise
*** =key3: 3a0d6fb5d2

*** =instructions3
Get films released in the 90s.
*** =solution3
```
SELECT title, release_year
FROM films
WHERE release_year >= 1990 AND release_year <= 2000;
```
*** =sct3
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type4: NormalExercise
*** =key4: c8c0fd95a2

*** =instructions4
Get average duration for films released in the UK or which were released in 2012.
*** =solution4
```
SELECT AVG(duration)
FROM films
AS average_duration
WHERE release_year = 2012
OR COUNTRY = 'UK';
```
*** =sct4
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='average_duration', match='exact')
Ex().has_equal_ast()
```

--- type:TabExercise lang:sql xp:100 skills:1 key:9c11f67712
## BETWEEN (A Rock and A Hard Place)
Simple BETWEEN exercises.

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: b923abef23

*** =instructions1
Get films released in the 90s.
*** =solution1
```
SELECT title, release_year
FROM films
WHERE release_year BETWEEN 1990 AND 2000;
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='title', match='any')
Ex().test_column(name='release_year', match='any')
Ex().has_equal_ast()
```

*** =type2: NormalExercise
*** =key2: feccadb369

*** =instructions2
Get the number of films released in the 90s.
*** =solution2
```
SELECT COUNT(*)
FROM films
WHERE release_year BETWEEN 1990 AND 2000;
```
*** =sct2
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

*** =type3: NormalExercise
*** =key3: 3b8e19a819

*** =instructions3
Get the number of films made between 2000 and 2015 with budgets over $100 million.
*** =solution3
```
SELECT title, budget
FROM films
WHERE release_year
BETWEEN 2000 AND 2015
AND budget > 100000000;
```
*** =sct3
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='title', match='any')
Ex().test_column(name='budget', match='any')
Ex().has_equal_ast()
```

--- type:TabExercise lang:sql xp:100 skills:1 key:4fc7e638f8
## WHERE IN The World
Exercises using WHERE with IN

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: 94bded8f60

*** =instructions1
Get films released in  in 1990 or released in 2000 that were longer than two hours.
*** =solution1
```
SELECT title, release_year
FROM films
WHERE release_year IN (1990, 2000)
AND duration > 120;
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='title', match='any')
Ex().test_column(name='release_year', match='any')
Ex().has_equal_ast()
```


--- type:TabExercise lang:sql xp:100 skills:1 key:84411d78aa
## BETWEEN and AND
Exercises using BETWEEN with AND.

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: c690de7be7

*** =instructions1
Get the number of films released between 2000 and 2015 that were longer than two hours.
*** =solution1
```
SELECT COUNT(*)
FROM films
WHERE release_year BETWEEN 2000 AND 2015
AND duration > 120;
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().has_equal_ast()
```

--- type:TabExercise lang:sql xp:100 skills:1 key:84411d78ab
## IS NULL
Simple exercises.

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: 2ac524310b

*** =instructions1
Get the names of people who are still alive.
*** =solution1
```
SELECT name
FROM people
WHERE deathdate IS NULL;
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='name', match='any')
Ex().has_equal_ast()
```

--- type:TabExercise lang:sql xp:100 skills:1 key:84411d78ac
## LIKE and NOT LIKE
Simple exercises.

*** =pre_exercise_code
```{python}
connect('postgresql', 'films')
```

*** =sample_code
```{sql}
Sample code goes here.
```

*** =type1: NormalExercise
*** =key1: c796fe8702

*** =instructions1
Get people whose names begin with 'B'.
*** =solution1
```
SELECT name
FROM people
WHERE name LIKE 'B%';
```
*** =sct1
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='name', match='any')
Ex().has_equal_ast()
```

*** =type2: NormalExercise
*** =key2: 7a0dea480b

*** =instructions2
Get people whose names have 'r' as the second letter.
*** =solution2
```
SELECT name
FROM people
WHERE name LIKE '_r%';
```
*** =sct2
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='name', match='any')
Ex().has_equal_ast()
```

*** =type3: NormalExercise
*** =key3: a91126fd4d

*** =instructions3
Get people whose names don't start with A.
*** =solution3
```
SELECT name
FROM people
WHERE name NOT LIKE 'A%';
```
*** =sct3
```{sql}
Ex().check_result()
Ex().test_ncols()
Ex().test_nrows()
Ex().test_column(name='name', match='any')
Ex().has_equal_ast()
```