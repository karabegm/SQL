# SQL
/* Create table about the people and what they do here */
CREATE TABLE stars (id integer primary key autoincrement, name text, gender text, age integer);
INSERT INTO stars (name, gender, age) VALUES
    ("Sandra Bullock", "female", 56), ("Tom Hanks", "male", 66), ("Zendaya", "female", 26), ("Tom Holland", "male", 26), ("Chris Evans", "male", 41), ("Elizabeth Olsen", "female", 33);
    
CREATE TABLE movies (id integer primary key autoincrement, actor_id integer, movie_title text, date_released integer);

INSERT INTO movies (actor_id, movie_title, date_released) VALUES
    (1, "Bird Box", 2018), (1, "The Proposal", 2009), (2, "Toy Story", 1995), (2, "The Terminal", 2004), (3, "The Greatest Showman", 2017), (3, "SM: No Way Home", 2021), (4, "CA: Civil War",2016), (4, "Uncharted", 2022), (5, "Gifted", 2017), (5, "Before We Go", 2014), (6, "Avengers IW", 2018);
    
CREATE TABLE costar (id integer primary key autoincrement, actor_id integer, co_star_id integer);

INSERT INTO costar (actor_id, co_star_id) VALUES 
(1, NULL), (2, NULL), (3, 4), (4, 3), (5, 6), (6, 5);

SELECT stars.name, movies.movie_title FROM stars
JOIN MOVIES ON stars.id=movies.actor_id;

SELECT stars.name, movies.movie_title as movies_after_2010 FROM stars
JOIN MOVIES ON stars.id=movies.actor_id 
WHERE movies.date_released>2010;

SELECT stars.name, co_star.name as co_star from stars
join costar on stars.id=costar.actor_id
left outer join stars co_star on co_star.id=costar.co_star_id;




    
