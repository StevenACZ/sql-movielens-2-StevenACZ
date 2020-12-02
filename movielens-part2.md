# MovieLens Part 2

Copy and paste you SQL query replacing the lines `<your SQL query here>` inside each question.

0. List the `title` and `genres` of all movies.

```SQL
SELECT m.title, g.name AS "genre" FROM movies AS m
JOIN genres_movies AS gm ON m.id = gm.movie_id
JOIN genres AS g ON gm.genre_id = g.id;
```

1. List all the users ids and their occupation

```SQL
SELECT us.id, oc.name FROM users AS us
JOIN occupations AS oc ON us.occupation_id = oc.id;
```

2. List the number of movies group by genre

```SQL
<your SQL query here>
```

3. Retrieve only the genre which have more movies associated.

```SQL
<your SQL query here>
```

4. List all the movies titles and the number of genres each movie has associated.

```SQL
<your SQL query here>
```

5. List the number of users by occupation.

```SQL
<your SQL query here>
```

6. List the movie title and their average rating sorted from the most liked to the less liked.

```SQL
<your SQL query here>
```

7. List the average rating per genre.

```SQL
<your SQL query here>
```

8. Retrieve the most popular movie from 1995.

```SQL
<your SQL query here>
```

9. Retieve the average age of the users who have rated the movie "Eye for an Eye (1996)"

```SQL
<your SQL query here>
```

10. List the top 10 movies for Lawyers released between 1990 and 1995.

```SQL
<your SQL query here>
```
