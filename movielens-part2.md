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
SELECT g.name AS "genres", COUNT(*) AS "cant_movies" FROM  movies AS m
JOIN genres_movies AS gm ON m.id = gm.movie_id
JOIN genres AS g ON gm.genre_id = g.id GROUP BY g.name;
```

3. Retrieve only the genre which have more movies associated.

```SQL
SELECT g.name AS "genres", COUNT(*) AS "cant_movies" FROM  movies AS m
JOIN genres_movies AS gm ON m.id = gm.movie_id
JOIN genres AS g ON gm.genre_id = g.id
GROUP BY g.name
ORDER BY cant_movies DESC
LIMIT 1;
```

4. List all the movies titles and the number of genres each movie has associated.

```SQL
SELECT m.title, COUNT(*) AS "cant_of_genres_associated" FROM movies AS m
JOIN genres_movies AS gm ON m.id = gm.movie_id
JOIN genres AS g ON g.id = gm.genre_id
GROUP BY m.title;
```

5. List the number of users by occupation.

```SQL
SELECT ocu.name, COUNT(*) AS "users_by_occupation" FROM users AS us
JOIN occupations AS ocu ON us.occupation_id = ocu.id
GROUP BY ocu.name;
```

6. List the movie title and their average rating sorted from the most liked to the less liked.

```SQL
SELECT m.title, ROUND(AVG(ra.rating), 2) AS "average_rating" FROM movies AS m
JOIN ratings AS ra ON ra.movie_id = m.id
GROUP BY m.title
ORDER BY average_rating DESC;
```

7. List the average rating per genre.

```SQL
SELECT g.name, ROUND(AVG(ra.rating), 2) AS "average_rating" FROM genres_movies AS gm
JOIN genres AS g ON g.id = gm.genre_id
JOIN ratings AS ra ON ra.movie_id = gm.movie_id
GROUP BY g.name
ORDER BY average_rating DESC;
```

8. Retrieve the most popular movie from 1995.

```SQL
SELECT m.title, ra.rating AS "rating", EXTRACT(YEAR FROM m.release_date) AS "release_data" FROM movies AS m
JOIN ratings AS ra ON ra.movie_id = m.id
WHERE EXTRACT(YEAR FROM m.release_date) = 1995
ORDER BY ra.rating DESC
LIMIT 1;
```

9. Retieve the average age of the users who have rated the movie "Eye for an Eye (1996)"

```SQL
<your SQL query here>
```

10. List the top 10 movies for Lawyers released between 1990 and 1995.

```SQL
<your SQL query here>
```

```
             List of relations
 Schema |     Name      | Type  |  Owner
--------+---------------+-------+----------
 public | genres        | table | postgres
 public | genres_movies | table | postgres
 public | movies        | table | postgres
 public | occupations   | table | postgres
 public | ratings       | table | postgres
 public | users         | table | postgres
 ```