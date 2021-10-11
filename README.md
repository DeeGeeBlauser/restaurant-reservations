# Restaurant Reservation System - Periodic Tables

## Table of contents
- [General Info](#general-info)
  - [Link to live application](#link-to-live-application)
  - [Summary of application](#summary-of-application)
- [REST API](#rest-api)
- [Technologies](#technologies)
- [Installation](#installation)

## General Info

### Link to live application
> https://db-capstone-front-end.herokuapp.com/dashboard

### Summary of application

> This application is a reservation system for fine dining restaurants.
> The software is used only by restaurant personnel when a customer calls to request a reservation.
> At this point, the customers will not access the system online.\
> The user has access to navigate to four different pages from the MENU\
> \
> "Dashboard" will show all current reservations, along with their status, and all tables, along with their status, for a given day.
>   If a reservation is shown for the current day, and has not occurred yet, the user may edit, cancel, or seat the reservation.\
>   Seating the reservation will take the user to a new page, where they will select the table to seat the reservation at.\
>   If a table is currently occupied, the user may free up the table by clicking the "Finish" option within the table's row

<img width="1433" alt="Screen Shot 2021-10-06 at 2 42 08 PM" src="https://user-images.githubusercontent.com/82486225/136273383-132f4103-e9d9-452d-9639-2cd28bfbb2c0.png">



> "Search" will allow the user to search for a reservation by mobile number

<img width="1429" alt="Screen Shot 2021-10-06 at 2 40 51 PM" src="https://user-images.githubusercontent.com/82486225/136273615-715ef84b-00e0-438e-ba92-fef6353e4df5.png">

> "New Reservation" allows the user to create and add a new reservation into the database

<img width="1429" alt="Screen Shot 2021-10-06 at 2 41 04 PM" src="https://user-images.githubusercontent.com/82486225/136273646-dbdc22cd-da02-4467-b41f-d3be7f170b4d.png">

> "New Table" allows the user to create and add a new table into the database

<img width="1403" alt="Screen Shot 2021-10-06 at 2 41 14 PM" src="https://user-images.githubusercontent.com/82486225/136273695-f19e74be-59d8-4ca3-9752-59881585e53f.png">


## Rest API

> The REST API for the Periodic Tables Reservation System App is described below.

### Get list of reservations

#### Request

`GET /reservations/`

#### Response

```
Status: 200 OK

 []
```

### Create new reservation

#### Request

`POST /reservations/`

#### Response

```
Status: 201 Created

{
            "reservation_id": 1,
            "created_at": "2020-12-10T08:30:32.326Z",
            "updated_at": "2020-12-10T08:30:32.326Z",
            "first_name": "Rick",
            "last_name": "Sanchez",
            "mobile_number": "202-555-0164",
            "people": 6,
            "reservation_date": "2020-12-31T06:00:00.000Z",
            "reservation_time": "20:00:00",
            "status": null
        }
```

### Get information on specific reservation by reservation_id

#### Request

`GET /reservations/:reservation_id`

#### Response

```
Status: 200 OK

{
        "reservation_id": 2,
        "created_at": "2020-12-10T08:31:32.326Z",
        "updated_at": "2020-12-10T08:31:32.326Z",
        "first_name": "Frank",
        "last_name": "Palicky",
        "mobile_number": "202-555-0153",
        "people": 1,
        "reservation_date": "2020-12-30T06:00:00.000Z",
        "reservation_time": "20:00:00",
        "status": null
    }
```

### Edit existing reservation by reservation_id

#### Request

`PUT /reservations/:reservation_id`

#### Response

```
Status: 200 OK

{
        "reservation_id": 2,
        "created_at": "2020-12-10T08:31:32.326Z",
        "updated_at": "2020-12-10T08:31:32.326Z",
        "first_name": "Frank",
        "last_name": "Palicky",
        "mobile_number": "202-555-0153",
        "people": 4,
        "reservation_date": "2020-12-30T06:00:00.000Z",
        "reservation_time": "20:00:00",
        "status": null
    }

```

### Update reservation status by reservation_id

#### Request

`PUT /reservations/:reservation_id/status`

#### Response

```
Status: 200 OK

{
        "reservation_id": 2,
        "created_at": "2020-12-10T08:31:32.326Z",
        "updated_at": "2020-12-10T08:31:32.326Z",
        "first_name": "Frank",
        "last_name": "Palicky",
        "mobile_number": "202-555-0153",
        "people": 4,
        "reservation_date": "2020-12-30T06:00:00.000Z",
        "reservation_time": "20:00:00",
        "status": "canceled"
    }

```

### Get list of tables

#### Request

`GET /tables/`

#### Response

```
Status: 200 OK

 []
```

### Create new table

#### Request

`POST /tables/`

#### Response

```
Status: 201 Created

 {
            "table_id": 3,
            "table_name": "#1",
            "capacity": 6,
            "status": "free",
            "reservation_id": null,
            "created_at": "2021-10-01T16:29:47.220Z",
            "updated_at": "2021-10-01T16:29:47.220Z"
        }
```

### Update table status to be seated

#### Request

`PUT /tables/:table_id/seat`

#### Response

```
Status: 200 OK

{
            "table_id": 3,
            "table_name": "#1",
            "capacity": 6,
            "status": "seated",
            "reservation_id": null,
            "created_at": "2021-10-01T16:29:47.220Z",
            "updated_at": "2021-10-01T16:29:47.220Z"
        }
```

### Update table status to finished

#### Request

`DELETE /tables/:table_id/seat`

#### Response


```
Status: 200 OK

{
            "table_id": 3,
            "table_name": "#1",
            "capacity": 6,
            "status": "finished",
            "reservation_id": null,
            "created_at": "2021-10-01T16:29:47.220Z",
            "updated_at": "2021-10-01T16:29:47.220Z"
        }
```


## Technologies
Project is created with:
* React.js
* CSS
* Bootstrap
* Node.js
* Express
* Knex
* PostgreSQL


## Installation

1. Fork and clone this repository.
1. Run `cp ./back-end/.env.sample ./back-end/.env`.
1. Update the `./back-end/.env` file with the connection URL's to your ElephantSQL database instance.
1. Run `cp ./front-end/.env.sample ./front-end/.env`.
1. You should not need to make changes to the `./front-end/.env` file unless you want to connect to a backend at a location other than `http://localhost:5000`.
1. Run `npm install` to install project dependencies.
1. Run `npm run start:dev` to start your server in development mode.


