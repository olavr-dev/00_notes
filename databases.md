# Databases

We use databases to perform **CRUD (Create, Read, Update, Delete)** operations more efficiently.

**(DBMS)** Database management systems are software systems optimized for data storage tasks.

- Optimize simultaneous read / write access.
- Optimize data storage and retrieval.
- Optimize data querying (e.g. rich queries with filters and conditions.)

## Main Database Systems

## Relational Database Management Systems (SQL)

SQL stands for Structured Query Language and was originally called "Sequel". Sequel is a language for structuring and storing data.

### Store normalized data across multiple tables

|               | Airports  |               |
| ------------- | --------- | ------------- |
| **ID**        | **City**  | **Country**   |
| MUC           | Munich    | Germany       |
| JFC           | New York  | United States |
| BCN           | Barcelona | Spain         |
| Unique String | String    | String        |

|                | Flights       |                 |
| -------------- | ------------- | --------------- |
| **ID**         | **Departure** | **Destination** |
| 123            | MUC           | JFK             |
| 331            | BCN           | MUC             |
| 591            | JFK           | BCN             |
| Unique Integer | String        | String          |

Tables have clearly defined _schemas and data types_

Data and relations can be _queried_

**_"Get data on all flights that depart in MUC"_**

This will get Flight ID, Departure and Destination from the Flights Table, but also City and Country from the Airports Table.

## Non-Relational Database Management Systems (NoSQL)

NoSQL databases does not use Sequel (obviously) for structuring and storing data, but use a various number of other languages to do the job.

### Flights

```json
{
  "FlightCode": 123,
  "Departure": {
    "APCode": "MUC",
    "APCity": "Munich",
    "APCountry": "Germany"
  },
  "Destination": {
    "APCode": "JFK",
    "APCity": "New York",
    "APCountry": "United States"
  }
}
```

```json
{
  "FlightCode": 331,
  "Departure": {
    "APCode": "BCN",
    "APCity": "Barcelona",
    "APCountry": "Spain"
  },
  "Destination": {
    "APCode": "MUC",
    "APCity": "Munich",
    "APCountry": "Germany"
  }
}
```

```json
{
  "FlightCode": 591,
  "Departure": {
    "APCode": "JFK",
    "APCity": "New York",
    "APCountry": "United States"
  },
  "Destination": {
    "APCode": "BCN",
    "APCity": "Barcelona",
    "APCountry": "Spain"
  }
}
```

Data is stored in only a few tables which each contain more information. This enables data to be fetched with fewer queries.

## SQL vs NoSQL - Which One To Choose?

There is no clear winner. They are both very popular.

Both systems can be used for any given use-case.

### You need to think about the queries you'll be running when choosing

**SQL** databases provide more structure and rules. Can have scalability issues on very large websites.

**NoSQL** databases can be more flexible and reduce amount of require queries.

You can use both a the same time as well.

## Popular SQL Systems

### MySQL

Open Source - The most popular SQL database system.

### PostgreSQL

Open Source - Also very popular.

### Microsoft SQL

Closed Source - Requires a commercial license.
