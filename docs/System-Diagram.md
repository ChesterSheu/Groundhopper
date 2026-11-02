# Groundhopper: System Design

## Application Architecture

Groundhopper will be a Java terminal application that allows users to manage football stadiums and record their matchday experiences.

The application will be divided into several main components:

- Terminal Menu: Displays available options and collects user input.
- Main Application: Coordinates the different parts of the program.
- Stadium Manager: Adds, searches, displays, and manages stadium information.
- Visit Manager: Records and manages matches attended.
- Statistics Manager: Calculates totals, averages, and other groundhopping statistics.
- File Manager: Saves and loads information from CSV files.

## Data Organization

Groundhopper will use two main types of records: Stadiums and Visits.

Each stadium will contain:
- Unique stadium ID
- Stadium name
- City
- Country
- Home club
- Capacity

Each visit will contain:
- Unique visit ID
- Stadium ID
- Match date
- Home team
- Away team
- Competition
- Final score
- Atmosphere rating
- Stadium appearance rating
- Overall experience rating
- Personal notes

## Data Relationships

A stadium can have multiple recorded visits. Each visit will reference a stadium through its unique stadium ID.

For example, a user might visit the same stadium five different times. Instead of creating five separate stadium records, Groundhopper will store one stadium record and connect all five visits to it.

## Data Storage

The application will use two CSV files:

- stadiums.csv: Stores information about football stadiums.
- visits.csv: Stores information about matches attended and personal experiences.

The File Manager will handle reading and writing information so that user data remains available after the application closes.

## Design Decisions

Java was selected because it is the primary language used in my coursework and allows me to apply concepts learned in class.

CSV files were selected because they provide a simple way to store information without requiring an external database.

The terminal interface will keep the initial application manageable and allow more time to focus on the actual functionality.

Separating stadiums and visits will also reduce duplicated information and make it easier to calculate statistics and organize match history.