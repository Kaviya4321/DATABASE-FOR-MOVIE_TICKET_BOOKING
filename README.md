MOVIES TICKET BOOKING
This will help the users to generate database on ticket booking for movies  and also useful for the people,when the people want to spend their timing by watching movie in theatre  this will help them to indentify the availability of the tickets in particular theatre.
MODULES :
•	Users
•	Movies
•	Theaters
•	Movie_schedules
•	bookings

CREATE DATABASE  movie_ticket_booking;

-- Use the database
USE movie_ticket_booking;

--Table for storing users
CREATE  TABLE  users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL
);

-- Table for storing movies
CREATE  TABLE  movies (
    movie_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100) NOT NULL,
    director VARCHAR(100),
    release_date DATE,
    genre VARCHAR(50),
);
-- Table for storing theaters
CREATE TABLE theaters (
    theater_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
 location VARCHAR(100) NOT NULL
);
-- Table for storing movie_schedules
CREATE TABLE movie_schedules (
    schedule_id INT AUTO_INCREMENT PRIMARY KEY,
    movie_id INT,
    theater_id INT,
    start_time DATETIME,
    FOREIGN KEY (movie_id) REFERENCES movies(movie_id),
    FOREIGN KEY (theater_id) REFERENCES theaters(theater_id)
);
-- Table for storing bookings
CREATE   TABLE  bookings (
    booking_id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    schedule_id INT,
    seat_number VARCHAR(10),
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (schedule_id) REFERENCES movie_schedules(schedule_id)
);
INSERT INTO users (username, password, email) VALUES
('user1', 'password1', 'user1@example.com'),
('user2', 'password2', 'user2@example.com'),
('user3', 'password3', 'user3@example.com'),
('user4', 'password4', 'user4@example.com'),
('user5', 'password5', 'user5@example.com'),
('user6', 'password6', 'user6@example.com'),
('user7', 'password7', 'user7@example.com'),
('user8', 'password8', 'user8@example.com'),
('user9', 'password9', 'user9@example.com'),
('user10', 'password10', 'user10@example.com');

INSERT INTO movies (title, director, release_date, genre, description) VALUES
('The Shawshank Redemption', 'Frank Darabont', '1994-09-22', 'Drama'),
('The Godfather', 'Francis Ford Coppola', '1972-03-24', 'Crime, Drama'),
('The Dark Knight', 'Christopher Nolan', '2008-07-18', 'Action, Crime, Drama'),
('Pulp Fiction', 'Quentin Tarantino', '1994-10-14', 'Crime, Drama'),
('Schindler\'s List', 'Steven Spielberg', '1994-02-04', 'Biography, Drama, History'),
('Forrest Gump', 'Robert Zemeckis', '1994-07-06', 'Drama, Romance'),
('The Lord of the Rings: The Return of the King', 'Peter Jackson', '2003-12-17', 'Action, Adventure, Drama'),
('Inception', 'Christopher Nolan', '2010-07-16', 'Action, Adventure, Sci-Fi'),
('The Matrix', 'Lana Wachowski, Lilly Wachowski', '1999-03-31', 'Action, Sci-Fi'),
('Fight Club', 'David Fincher', '1999-10-15', 'Drama');


INSERT INTO theaters (name, location) VALUES
('Cineplex Cinemas', '123 Main Street, Cityville'),
('Regal Cinemas', '456 Elm Street, Townsville'),
('AMC Theatres', '789 Oak Street, Villageton'),
('Cinemark Theatres', '101 Pine Street, Hamletville'),
('Vue Cinemas', '234 Maple Street, Boroughburg'),
('Odeon Cinemas', '567 Cedar Street, Villagetown'),
('ArcLight Cinemas', '890 Birch Street, Metropolis'),
('Landmark Theatres', '111 Spruce Street, Hamletown'),
('Alamo Drafthouse Cinema', '222 Oakwood Street, Cityburg'),
('Palace Cinemas', '333 Pinecrest Street, Villagetown');

INSERT INTO theaters (name, location) VALUES
('Cineplex Cinemas', '123 Main Street, Cityville'),
('Regal Cinemas', '456 Elm Street, Townsville'),
('AMC Theatres', '789 Oak Street, Villageton'),
('Cinemark Theatres', '101 Pine Street, Hamletville'),
('Vue Cinemas', '234 Maple Street, Boroughburg'),
('Odeon Cinemas', '567 Cedar Street, Villagetown'),
('ArcLight Cinemas', '890 Birch Street, Metropolis'),
('Landmark Theatres', '111 Spruce Street, Hamletown'),
('Alamo Drafthouse Cinema', '222 Oakwood Street, Cityburg'),
('Palace Cinemas', '333 Pinecrest Street, Villagetown');


INSERT INTO movie_schedules (movie_id, theater_id, start_time) VALUES
(1, 1, '2024-03-11 18:00:00'),
(2, 2, '2024-03-12 15:30:00'),
(3, 3, '2024-03-12 20:00:00'),
(4, 4, '2024-03-13 19:00:00'),
(5, 5, '2024-03-13 21:15:00'),
(6, 6, '2024-03-14 14:00:00'),
(7, 7, '2024-03-14 17:30:00'),
(8, 8, '2024-03-15 18:45:00'),
(9, 9, '2024-03-16 20:30:00'),
(10, 10, '2024-03-17 16:45:00');

INSERT INTO bookings (user_id, schedule_id, seat_number) VALUES
(1, 1, 'A1'),
(2, 2, 'B3'),
(3, 3, 'C5'),
(4, 4, 'D2'),
(5, 5, 'E7'),
(6, 6, 'F4'),
(7, 7, 'G8'),
(8, 8, 'H6'),
(9, 9, 'I9'),
(10, 10, 'J10');

