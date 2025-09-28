# Event-Booking-ticketing-
🎟️ All-in-one PHP Event Booking &amp; Ticketing System for  Classes. Responsive frontend with HTML/CSS/JS, PHP backend connected to AWS RDS. Users can view events, book tickets, and get instant confirmation — all in one file, fully hosted on AWS EC2



# 🎟️ Event Booking & Ticketing System – Mahesh Classes

> A complete **all-in-one PHP application** to manage and book events for Mahesh Classes.  
> Frontend built with HTML/CSS/JS, backend in PHP connected to **AWS RDS MySQL** and hosted on **AWS EC2**.  
> Users can view upcoming events, book tickets, and get an instant confirmation page — all in one file.

---


## ✨ Features

- 📅 Display upcoming events with name, description, date, time, seats & price
- 📝 Booking form inside each event card
- 💾 Bookings saved directly to AWS RDS MySQL
- 🎉 Attractive confirmation page after booking
- ☁️ Fully hosted on AWS EC2 (Nginx + PHP-FPM)
- 📱 Responsive design that works on mobile & desktop

---
*

---

## 🛠️ Tech Stack

| Layer         | Technology |
| ------------- | ----------- |
| Frontend      | HTML, CSS, JavaScript (Bootstrap 5) |
| Backend       | PHP (single file) |
| Database      | AWS RDS MySQL |
| Hosting       | AWS EC2 Amazon Linux with Nginx |

---


---

## 📝 Setup Guide

Follow these steps to deploy the project yourself:

1. **Create Database on AWS RDS**
   ```sql
   CREATE DATABASE event_booking;
   USE event_booking;

   CREATE TABLE events (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(100) NOT NULL,
     description TEXT,
     date DATE NOT NULL,
     time TIME NOT NULL,
     total_seats INT NOT NULL,
     price DECIMAL(10,2) NOT NULL,
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );

   CREATE TABLE bookings (
     id INT AUTO_INCREMENT PRIMARY KEY,
     event_id INT NOT NULL,
     name VARCHAR(100) NOT NULL,
     email VARCHAR(100) NOT NULL,
     tickets INT NOT NULL,
     total_amount DECIMAL(10,2) NOT NULL,
     booked_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
     FOREIGN KEY (event_id) REFERENCES events(id)
   );

   INSERT INTO events (name, description, date, time, total_seats, price) VALUES
   ('Cloud Workshop','Learn AWS Cloud basics','2025-10-10','10:00:00',50,500.00),
   ('MERN Bootcamp','Full Stack MERN training','2025-10-15','14:00:00',40,1000.00),
   ('Data Analytics Seminar','Intro to Data Analytics','2025-10-20','11:00:00',30,700.00);


   2. Upload File to EC2

  .Upload event_booking.php to /usr/share/nginx/html on your EC2 server.

  3.Configure Database in File
   .Edit the top of event_booking.php and put your RDS endpoint, username and password.


📸 Screenshots

<img width="856" height="476" alt="image" src="https://github.com/user-attachments/assets/e3024044-67e0-4428-b24a-e6a9c5d5e106" />

<img width="868" height="438" alt="image" src="https://github.com/user-attachments/assets/43b5f842-1bc4-4ea6-b744-9560409882c5" />

<img width="776" height="311" alt="image" src="https://github.com/user-attachments/assets/871aaf23-e97d-4e60-a367-09d67fcbe000" />


