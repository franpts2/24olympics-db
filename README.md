# '24 Olympic Games Database

A relational database for the 2024 Olympic Games, with schema, sample data, and SQL queries.

> **Fork:** Fork of [pedroafmonteiro/project-bd-leic](https://github.com/pedroafmonteiro/project-bd-leic). The original project has no license file; this fork keeps the original attribution.

<p align="left">
  <img src="https://img.shields.io/badge/Sqlite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite">
</p>

## About

This project implements a relational database for managing information related to the Olympic Games: committees, people, athletes, coaches, venues, disciplines, stages, results, medals, and records.

## Project Structure

The project currently consists of the following SQL scripts:

*   **`create2.sql`**: The main SQL script to create the database schema. It defines all tables, primary keys, foreign keys, and constraints.
*   **`populate2.sql`**: A script to populate the database with sample data. It automatically initializes the schema by reading `create2.sql` before inserting data.
*   **`create1.sql`** & **`populate1.sql`**: Earlier or alternative versions of the creation and population scripts.

## Database Schema

The database models the following entities and relationships:

*   **Committee**: Represents National Olympic Committees (e.g., USA, CHN).
*   **Person**: Base entity for individuals, storing common attributes like name, gender, nationality, and birthdate.
*   **Athlete**: A specialization of `Person`, storing physical attributes (height, weight, BMI).
*   **Coach**: A specialization of `Person`, storing their role (Head, Assistant, etc.).
*   **Venue**: Locations where olympic events take place.
*   **AthleticDiscipline**: Different sports disciplines (e.g., 100m Sprint, Long Jump).
*   **Stage**: Specific stages of a competition (e.g., Finals, Heats).
*   **Result**: Performance metrics (time, distance, position) for athletes in specific stages.
*   **Medal**: Tracks medals (Gold, Silver, Bronze) won by athletes.
*   **Record**: Information about World and Olympic records.

## Usage

To use this database, you need **SQLite3** installed on your system.

### Running the scripts

You can create and populate the database by running the `populate2.sql` script within specific database file (e.g., `olympics.db`):

```bash
sqlite3 olympics.db < populate2.sql
```

Alternatively, you can open the database interactively:

```bash
sqlite3 olympics.db
```

And then inside the SQLite prompt:

```sql
.read populate2.sql
```

### Querying the Database

Once the database is populated, you can run SQL queries. For example, to select all athletes:

```sql
SELECT * FROM Athlete;
```

To see all people and their committees:

```sql
SELECT Person.pName, Committee.comName 
FROM Person 
JOIN Committee ON Person.comID = Committee.comID;
```

## Team & Course

**Team**

This project was developed by:

- [Francisca Portugal](https://github.com/franpts2)
- [João Lopes](https://github.com/joaolopes15)
- [Pedro Monteiro](https://github.com/pedroafmonteiro)

**Course**

Developed for the **BD (Databases)** course in 2024/2025 at FEUP (Faculty of Engineering, University of Porto).

## License

Coursework submitted at FEUP. Shared for reference; all rights reserved unless stated otherwise.

---

_24 Olympics — the Games, normalized._
