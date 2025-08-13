# 🎬 Movie Database Challenge

This project is a simple SQL database that stores information about **movies** and **actors**.

## 📌 Overview
The database contains two main tables:
1. **Actors** — stores details about each actor.
2. **Movies** — stores details about each movie.
An optional **Movie_Actors** table can be added to link actors to the movies they have acted in.

## 🗂 Table Structures

### Actors Table
| Column | Type        | Description |
|--------|------------|-------------|
| id     | INT (PK)   | Unique ID for each actor |
| name   | VARCHAR(100) | Actor's name |
| age    | INT        | Actor's age |

### Movies Table
| Column | Type        | Description |
|--------|------------|-------------|
| id     | INT (PK)   | Unique ID for each movie |
| title  | VARCHAR(200) | Name of the movie |
| year   | INT        | Release year of the movie |

### Optional: Movie_Actors Table
| Column   | Type | Description |
|----------|------|-------------|
| movie_id | INT  | References Movies(id) |
| actor_id | INT  | References Actors(id) |

## 💻 SQL Code

```sql
-- Create the Actors table
CREATE TABLE Actors (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT
);

-- Create the Movies table
CREATE TABLE Movies (
    id INT PRIMARY KEY,
    title VARCHAR(200),
    year INT
);

-- Optional: Create link table for actors and movies
CREATE TABLE Movie_Actors (
    movie_id INT,
    actor_id INT,
    FOREIGN KEY (movie_id) REFERENCES Movies(id),
    FOREIGN KEY (actor_id) REFERENCES Actors(id),
    PRIMARY KEY (movie_id, actor_id)
);
