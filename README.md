# DZ5-6-
ДЗ
 CREATE TABLE IF NOT EXISTS albums (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  title VARCHAR(255),
  description TEXT,
  year INTEGER  
);


CREATE TABLE IF NOT EXISTS songs (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  title VARCHAR(255),
  duration INTEGER, 
  album_id INTEGER,
  FOREIGN KEY (album_id) REFERENCES albums(id)
);


CREATE TABLE IF NOT EXISTS authors (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  name VARCHAR(255),
  bio TEXT
);

-- Создаем таблицу связи между песнями и авторами
CREATE TABLE IF NOT EXISTS song_authors (
  song_id INTEGER,
  author_id INTEGER,
  PRIMARY KEY (song_id, author_id),
  FOREIGN KEY (song_id) REFERENCES songs(id),
  FOREIGN KEY (author_id) REFERENCES authors(id)
);


INSERT INTO albums (title, description, year) VALUES
('Thriller', 'Best-selling album of all time', 1982),
('Back in Black', 'One of the best-selling albums ever', 1980);


INSERT INTO authors (name, bio) VALUES
('Michael Jackson', 'King of Pop'),
('Angus Young', 'AC/DC lead guitarist');


INSERT INTO songs (title, duration, album_id) VALUES
('Billie Jean', 294, 1),
('Beat It', 258, 1),
('Thriller', 357, 1),
('Wanna Be Startin'' Somethin''', 363, 1),
('Human Nature', 246, 1),
('Back in Black', 255, 2),
('You Shook Me All Night Long', 210, 2),
('Hells Bells', 312, 2),
('Shoot to Thrill', 316, 2),
('Rock and Roll Ain''t Noise Pollution', 263, 2);


INSERT INTO song_authors (song_id, author_id) VALUES
(1, 1),
(2, 1),
(3, 1),
(4, 1),
(5, 1),
(6, 2),
(7, 2),
(8, 2),
(9, 2),
