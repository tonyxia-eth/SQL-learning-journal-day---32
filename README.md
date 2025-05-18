# CS50 SQL - Day 32: ATL Airport Database Schema

Today, despite feeling sick and working a full shift, I stayed committed to my SQL learning journey and completed Lesson 2 assignment from CS50’s Introduction to Databases.

### What I worked on:
- Designed a relational database schema for Hartsfield-Jackson Atlanta International Airport (ATL)
- Created tables for passengers, airlines, flights, and check-ins with proper constraints and foreign keys
- Practiced writing `CREATE TABLE` statements and linking tables via foreign keys
- Learned how to structure real-world data models for complex systems

### Challenges:
- Fighting a head cold while managing daily responsibilities
- Staying focused during a demanding day

### Next steps:
- Practice inserting data and querying this database
- Prepare for the upcoming CS50 SQL quizzes and hands-on challenges

---

## Commands used today

```bash
mkdir atl
cd atl
code schema.sql
sqlite3 atl.db
.read schema.sql


CREATE TABLE "passenger" (
    "id" INTEGER PRIMARY KEY,
    "name" TEXT NOT NULL,
    "age" INTEGER NOT NULL CHECK ("age" > 0)
);

CREATE TABLE "flights" (
    "id" INTEGER PRIMARY KEY,
    "origin" TEXT NOT NULL,
    "destination" TEXT NOT NULL,
    "departure_time" NUMERIC NOT NULL
);

CREATE TABLE "bookings" (
    "id" INTEGER PRIMARY KEY,
    "passenger_id" INTEGER NOT NULL,
    "flight_id" INTEGER NOT NULL,
    "booking_time" NUMERIC NOT NULL,
    FOREIGN KEY ("passenger_id") REFERENCES "passenger"("id"),
    FOREIGN KEY ("flight_id") REFERENCES "flights"("id")
);
