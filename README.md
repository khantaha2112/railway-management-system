# Railway Management System (RMS)

# Demo Admin
https://github.com/khantaha2112/railway-management-system/assets/110721493/7e86bc43-80fa-4b6b-8a36-d6a3d95b76bf

# Demo User Reg
https://github.com/khantaha2112/railway-management-system/assets/110721493/5303c4b2-0fe7-44a6-8d4e-d22929a5733d

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Setup](#setup)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Assumptions](#assumptions)


## Introduction

This project is a Railway Management System designed to emulate functionalities similar to IRCTC. Users can register, log in, search for trains between stations, check seat availability, and book seats. Admin users can add new trains and manage the train data.

## Features

- User Registration and Login
- Admin Role Management
- Add New Train (Admin Only)
- Get Seat Availability
- Book a Seat
- Get Booking Details
- Race Condition Handling for Simultaneous Bookings

## Tech Stack

- **Frontend:** HTML, CSS, JavaScript, Bootstrap
- **Backend:** PHP
- **Database:** MySQL

## Installation

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/khantaha2112/railway-management-system.git
   cd orrs
2. **Install XAMPP:**
- Download and install XAMPP from https://www.apachefriends.org/download.html
3. **Start Apache and MySQL:**
- Open XAMPP Control Panel and start Apache and MySQL
4. **Import Database:**
- Open PHPMyAdmin by navigating to http://localhost/phpmyadmin/.
- Create a new database named orrs_db.
- Import the database/orrs_db.sql file into the created database.
5. **Configure Database Connection:**
- Open config.php file.
- Set your MySQL database connection details
             <?php
             $servername = "localhost";
            $username = "root";
            $password = "";
            $dbname = "orrs_db";
            ?>
##  Setup
1. **Move Project to XAMPP htdocs:**
- Copy the entire project folder to C:/xampp/htdocs/.
2. **Configure Apache:**
- Open C:/xampp/apache/conf/httpd.conf.
- Set the DocumentRoot to the path of your project folder:
        DocumentRoot "C:/xampp/htdocs/orrs"
        <Directory "C:/xampp/htdocs/orrs">

## Usage 
1. **Access the Application:**
- Open your browser and navigate to http://localhost/orrs.
2. **User Registration:**
- Go to the Register page.
- Fill in the form and submit to create a new user account.
3. **User Login:**
- Go to the Login page.
- Enter your credentials to log in.
4. **User Login:**
- Log in as an admin user.
- Navigate to the Add Train page to add a new train.
- Only admin users can perform this action.
5. **Train Availability:**
- Go to the Train Availability page.
- Enter source and destination stations to check available trains and seat availability.
6. **Book a Seat:**
- Go to the Book Seat page.
- Enter train details to book a seat.
7. **Booking Details:**
 - Go to the Booking Details page.
 - Enter booking ID to fetch the booking details.
 
 ## API Endpoints
 1. **Register User:**
 - Endpoint: /api/auth/register.php.
 - Method: POST
 - Parameters: username, password, role
 
 2. **Login User:**
 - Endpoint: /api/auth/login.php
 - Method: POST
 - Parameters: username, password
 
  3. **Add Train:**
 - Endpoint: /api/train/add.php
 - Parameters: trainNumber, source, destination, totalSeats
 - Headers: x-api-key (Admin API key)

  4.**Get Seat Availability:**
 - Endpoint: /api/train/availability.php
 - Method: GET
 - Parameters: source, destination
 
 5.**Book a Seat:**
 - Endpoint: /api/booking/book.php
 - Method: POST
 - Parameters: trainId
 - Headers: Authorization (Bearer Token)
 
  4.**Get Booking Details:**
 - Endpoint: /api/booking/details.php
 - Method: GET
 - Parameters: bookingId
 - Headers: Authorization (Bearer Token)

## Assumptions
1.**Admin Private Key:**
- The Admin API key is hardcoded in the add.php file and should be kept secret.
- This can be stored in environment variables for better security.

2.**Simultaneous Bookings:**
- Race conditions are handled using SQL transactions and locking mechanisms to ensure only one booking is successful in case of simultaneous requests.
 






