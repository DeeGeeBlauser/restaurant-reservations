# Restaurant Reservation System - Periodic Tables

## Table of contents
* [General Info](#general-info)
*   [Link to live application](#link-to-live-application)
*   [Summary of application](#summary-of-application)
* [REST API](#rest-api)
* [Technologies](#technologies)
* [Installation](#installation)

## General Info

### Link to live application

### Summary of application

> This application is a reservation system for fine dining restaurants.
> The software is used only by restaurant personnel when a customer calls to request a reservation.
> At this point, the customers will not access the system online.
> The user has access to navigate to four different pages from the MENU
> "Dashboard" will show all current reservations, along with their status, and all tables, along with their status, for a given day.
>   If a reservation is shown for the current day, and has not occurred yet, the user may edit, cancel, or seat the reservation.
>   Seating the reservation will take the user to a new page, where they will select the table to seat the reservation at.
>   If a table is currently occupied, the user may free up the table by clicking the "Finish" option within the <table>
> "Search" will allow the user to search for a reservation by mobile number
> "New Reservation" allows the user to create and add a new reservation into the database
> "New Table" allows the user to create and add a new table into the database

## Rest API

> The REST API for the Periodic Tables Reservation System App is described below.

### Get list of reservations

#### Request

`GET /reservations/`

#### Response

### Create new reservation

#### Request

`POST /reservations/`

#### Response

### Get information on specific reservation by reservation_id

#### Request

`GET /reservations/:reservation_id`

#### Response

### Edit existing reservation by reservation_id

#### Request

`PUT /reservations/:reservation_id`

#### Response

### Update reservation status by reservation_id

#### Request

`PUT /reservations/:reservation_id/status`

#### Response

### Get list of tables

#### Request

`GET /tables/`

#### Response

### Create new table

#### Request

`POST /tables/`

#### Response

### Update table status to be seated

#### Request

`PUT /tables/:table_id/seat`

#### Response

### Update table status to finished

#### Request

`DELETE /tables/:table_id/seat`

#### Response


## Technologies
Project is created with:
* React.js
* CSS
* Node.js
* Express
* PostgreSQL


## Installation

1. Fork and clone this repository.
1. Run `cp ./back-end/.env.sample ./back-end/.env`.
1. Update the `./back-end/.env` file with the connection URL's to your ElephantSQL database instance.
1. Run `cp ./front-end/.env.sample ./front-end/.env`.
1. You should not need to make changes to the `./front-end/.env` file unless you want to connect to a backend at a location other than `http://localhost:5000`.
1. Run `npm install` to install project dependencies.
1. Run `npm run start:dev` to start your server in development mode.


