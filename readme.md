## MovieLens Part 2

This assignment consists of creating SQL queries that answer the questions on `movielens-part2.md`.

You already have the MovieLens Database in your local environment. You can connect using:

```bash
$ psql -d movielens
psql (13.0)
Type "help" for help.

movielens=#
```

From here you can start writing your queries:

```bash
movielens=# SELECT m.title, g.name as "genre" FROM movies as m
movielens-# JOIN genres_movies as gm ON m.id = gm.movie_id
movielens-# JOIN genres as g ON gm.genre_id = g.id;
-----------------------------------------------------------------------------------+-------------
 Toy Story (1995)                                                                  | Animation
 Toy Story (1995)                                                                  | Children's
 Toy Story (1995)                                                                  | Comedy
 GoldenEye (1995)                                                                  | Action
 GoldenEye (1995)                                                                  | Adventure
 GoldenEye (1995)                                                                  | Thriller
 Four Rooms (1995)                                                                 | Thriller
 Get Shorty (1995)                                                                 | Action
 Get Shorty (1995)                                                                 | Comedy
 Get Shorty (1995)                                                                 | Drama
 Copycat (1995)                                                                    | Crime
 Copycat (1995)                                                                    | Drama
 Copycat (1995)                                                                    | Thriller
 ...
```

> Don't forget to end your query with a `;`

If you want to use another management interface to interact with postgresql, we reccomend [pgAdmin](https://www.pgadmin.org/download/). Feel free to use the
management interface of your preference.

When you finish, commit your changes and push to your Github repo.

```
MovieLens data sets were collected by the GroupLens Research Project
at the University of Minnesota.

This data set consists of:
	* 100,000 ratings (1-5) from 943 users on 1682 movies.
	* Each user has rated at least 20 movies.
  * Simple demographic info for the users (age, gender, occupation, zip)

F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets:
History and Context. ACM Transactions on Interactive Intelligent
Systems (TiiS) 5, 4, Article 19 (December 2015), 19 pages.
DOI=http://dx.doi.org/10.1145/2827872
```
