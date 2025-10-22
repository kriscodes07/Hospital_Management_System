🏥 Hospital Appointment Management System (Java + MySQL)
📋 Overview

The Hospital Appointment Management System is a console-based Java application designed to simplify hospital operations by managing patients, doctors, and their appointments efficiently.
It uses JDBC (Java Database Connectivity) to connect with a MySQL database, allowing CRUD operations and real-time appointment scheduling directly from the terminal.

🚀 Features

✅ Add New Patients — register patients into the system.
✅ View All Patients — display all stored patient records.
✅ View All Doctors — list all registered doctors.
✅ Book Appointments — schedule patient appointments with available doctors.
✅ Check Doctor Availability — prevents double-booking of doctors on the same date.
✅ Database Integration — uses MySQL for storing and retrieving records.

🧩 Tech Stack

Language: Java

Database: MySQL

Connectivity: JDBC

IDE: IntelliJ IDEA / Eclipse (any Java IDE)

🏗️ Project Structure
Hospital-Appointment-System/
│
├── Main.java           # Main program (menu + logic control)
├── DbConnect.java      # Database connection utility
├── Patient.java        # Handles patient CRUD and validation
├── Doctor.java         # Handles doctor CRUD and validation
├── appointment table   # Stores booked appointments
└── README.md           # Project documentation

💡 How It Works

The user runs the program and selects an option from the console menu.

For booking, the system:

Checks if both patient and doctor exist.

Uses SQL to check if the doctor is already booked on that date.

If available, inserts a new appointment record into the appointment table.

The user can view, add, or manage records at any time.

🧠 Core Logic Example

Doctor availability check:

String query = "SELECT COUNT(*) FROM appointment WHERE doctor_id = ? AND appointment_date = ?";


If count == 0, the doctor is available; otherwise, the doctor is already booked.

📦 Database Tables

Table: doctor

Column	Type	Description
doctor_id	INT	Primary Key
name	VARCHAR(100)	Doctor’s name
specialization	VARCHAR(100)	Doctor’s field

Table: patient

Column	Type	Description
patient_id	INT	Primary Key
name	VARCHAR(100)	Patient’s name
age	INT	Patient’s age
gender	VARCHAR(10)	Gender

Table: appointment

Column	Type	Description
appointment_id	INT	Primary Key (auto increment)
patient_id	INT	Foreign key from patient table
doctor_id	INT	Foreign key from doctor table
appointment_date	DATE	Appointment date
🔧 Setup Instructions

Clone this repository:




Create the MySQL database and tables.

Update database credentials in DbConnect.java.

Run the program using your Java IDE or command line:

javac Main.java
java Main

🧰 Future Enhancements

Add appointment cancellation and rescheduling

Integrate with a GUI (JavaFX or Swing)

Add login roles (Admin, Doctor, Receptionist)

Use date validation and error handling

Export data to PDF/CSV reports

👨‍💻 Author


(Krishna Kumar Rana)
🎓 BCA (AIML Specialization)
💡 Passionate about Java, Backend Development, and AI-based Systems
