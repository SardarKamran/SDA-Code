Purpose:

This Java program allows you to view the fee payment history of a student by entering their Student ID. It connects to a MySQL database and fetches the payment details.

Prerequisites:

Before running this code, make sure you have the following installed and set up:

Java JDK 8 or later.
. MySQL Server.
. MySQL JDBC Driver (e.g., mysql-connector-java-x.x.xx.jar added to classpath).
. Any Java IDE (IntelliJ, Eclipse, NetBeans) or command-line tools.

Database Setup:

1) Open MySQL Workbench or MySQL CLI, then create the database and table:

CREATE DATABASE fee_management;

USE fee_management;

CREATE TABLE payments (
    payment_id INT AUTO_INCREMENT PRIMARY KEY,
    student_id INT NOT NULL,
    amount_paid DOUBLE NOT NULL,
    payment_date DATE NOT NULL
);

2) Insert some sample data (optional):

INSERT INTO payments (student_id, amount_paid, payment_date) VALUES
(1, 5000, '2024-01-10'),
(1, 4500, '2024-03-05'),
(2, 6000, '2024-02-20');

Configuration in Code:

Check and update these details in the code if needed:

private static final String DB_URL = "jdbc:mysql://localhost:3306/fee_management";
private static final String DB_USER = "root";
private static final String DB_PASSWORD = "";
Replace root and password with your MySQL credentials.

How to Run the Code:

Option 1: Using Command Line

. Save the code as ViewPaymentHistory.java
. Open terminal or command prompt.
. Navigate to the directory where your file is located.

. Compile the program:

javac -cp .;mysql-connector-java-8.0.xx.jar ViewPaymentHistory.java

. Run the program:

java -cp .;mysql-connector-java-8.0.xx.jar ViewPaymentHistory
Replace mysql-connector-java-8.0.xx.jar with the exact name of your JDBC driver.

Option 2: Using an IDE
. Create a new Java project.
. Add ViewPaymentHistory.java to the project.
. Add the MySQL JDBC driver to your project’s library/module dependencies.
. Run the main method.

Using the Program:

After running, the console will prompt:

=== View Payment History ===
Enter Student ID:
Enter a valid Student ID (e.g., 1) and press Enter.

The program will display all payment records for that student.
