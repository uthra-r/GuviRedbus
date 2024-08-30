# Source Code: 

1. RedbusScrape.ipynb
   1. This code is used to scrape the bus details from the Redbus and store in MySQL
2. streamlit.py
   1. This code is used to load data from MySQL and display using Streamlit

## Documentation:

Code has been updated with detailed comments

## Database Schema:

````mysql
CREATE TABLE IF NOT EXISTS bus_routes(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    route_name VARCHAR(250),
    route_link VARCHAR(250),
    bus_name VARCHAR(250),
    bus_type VARCHAR(250),
    departing_time TIME,
    duration VARCHAR(50),
    reaching_time TIME,
    star_rating DOUBLE(5,3),
    price DECIMAL(10,3),
    seats_available INT(10)
)
````

## Application with StreamLit

![Streamlit](https://github.com/uthra-r/GuviRedbus/blob/main/Streamlit.png?raw=true)



# Code File Documentation

## Introduction

This code file is designed to scrape bus route information from the RedBus website and store the data in a MySQL database. It utilizes Selenium for web automation, allowing it to navigate through multiple pages of bus routes and collect relevant details.

## File Overview

The file contains functions for connecting to a MySQL database, creating tables, inserting data, and scraping bus route details from a specified URL. The main function orchestrates the entire process from database connection to data collection and storage.

## Dependencies

The following external libraries are required to run this code file:

- **Selenium**: For web scraping and automation.
- **mysql-connector**: For connecting and interacting with a MySQL database.
- **python-dotenv**: For loading environment variables (if any).

## Key Components

The main components of this code file include:

- **connect_db**: Establishes a connection to the MySQL database.
- **create_db_table**: Creates the necessary database and table for storing bus routes.
- **insert_row**: Inserts a new record into the bus routes table.
- **getRouteDict**: Scrapes the bus route links and titles from the specified URL.
- **getBusDetails**: Collects detailed information about buses for each route and stores it in the database.
- **main**: The entry point of the program that orchestrates all processes.

## Input and Output

The expected inputs and outputs for this code file are:

- **Input**: A URL from which to scrape bus route information.
- **Output**: Data inserted into the MySQL database, including route names, links, bus names, types, departure times, durations, reaching times, star ratings, prices, and number of seats available.

## Code Structure

The code consists of several functions defined in a linear sequence, each performing a specific task. The main function at the end ties everything together, ensuring that the workflow from scraping to database insertion is executed seamlessly.

## Algorithm/Logic

The logic is as follows:

- Establish a database connection.
- Create a database and table if they don't already exist.
- Navigate to the bus route page and collect all available routes.
- For each route, gather detailed bus information by simulating clicks and scrolling to load all data.
- Insert the collected information into the MySQL database.

## Error Handling

The code includes basic error handling for database connection and insertion operations. If an error occurs during these processes, the code prints an error message and rolls back any changes to maintain data integrity.

## Examples/Usage

To use this code file:

1. Ensure that you have the necessary dependencies installed.
2. Update the database connection parameters as needed.
3. Run the code, which will automatically scrape bus information and store it in the specified database.

After execution, check your MySQL database for the **bus_routes** table containing the scraped data!



**Table Details**

| Name            | Data Type | Description                                      |
| :-------------- | :-------- | :----------------------------------------------- |
| id              | int       | Unique identifier for each bus route.AI          |
| route_name      | varchar   | Name of the bus route.AI                         |
| route_link      | varchar   | Link or URL to the route details.AI              |
| bus_name        | varchar   | Name of the bus operating on the route.AI        |
| bus_type        | varchar   | Type of bus used for the route.AI                |
| departing_time  | time      | Scheduled departure time of the bus.AI           |
| duration        | varchar   | Total travel duration of the bus route.AI        |
| reaching_time   | time      | Scheduled arrival time of the bus.AI             |
| star_rating     | double    | Rating of the bus route based on user reviews.AI |
| price           | decimal   | Cost of a ticket for the bus route.AI            |
| seats_available | int       | Number of available seats on the bus.            |
