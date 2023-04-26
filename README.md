# Introduction

This application is the db-based version of the Tip of the Day (TotD) application. The applications's basic use is for storing and displaying short flascards in command line for self learning. Each time user logs in to Linux command line, new tip of the day is displayed. The application here is the API service for delivering the data through HTTP/REST. This application contains also methods for updating the data.

# Installation

There are different approaches for installing and runnng the application.
Here is described the fully dockerized style.

## Docker version

### Prerequisites

Docker and docker-compose installed to the system.

### Steps

* Clone the project
* verify the values in docker-compose.yml are valid in your environment. 
  * Credentials can be changed for better security
  * Listening ports can be changed to avoid conflicts
* Start containers
* Run the initialization script for preloading some sample tips to the service

### Commands

Starting docker containers:
````
docker compose up -d
````
NOTE: run the command in the directory where the docker-compose.yml file resides.

Stopping containers:
````
docker compose down
````

# Add sample data to the database 

If you want to populate the DB with sample tips snippets:

Navigate to scripts and run command
````
npm install
````

Create .env file and verify it contains correct DB credentials and run
````
node add_data_to_db.js
````

# Try out - endpoints

## Read endpoints

Note some services provide plain text respose, some JSON data.
For the TotD Bash client the plain text endpoints are the most convenient to use.

Get tip by Id as plain text (GET) and can use any positive integer number as :tid value to fetch tip
````
http://localhost:3000/plain/:tid
````
Get all tips (GET)
````
http://localhost:3000/getall
````
Get tip by Id (GET)
````
http://localhost:3000/:tid
````
Get random tip by Id as plain text (GET) and can use any positive integer number as :tid value to fetch tip
````
http://localhost:3000/randomplain/:tid
````
Get number of tips
````
http://localhost:3000/nrtips
````

## Update endpoints

Delete tip by Id (DELETE)
````
http://localhost:3000/:tid/delete
````
Update tip by Id (PATCH)
````
http://localhost:3000/:tid/update
````
Add new tip (POST)
````
http://localhost:3000/addtip
````

# Postman screenshots

<div align="center">
    <p>Get tip by Id endpoint </p>
    <img src="/screenshots/getbyid_endpoint.png" width="600px"</img>
    <p>Get tip by Id plain text endpoint</p>
    <img src="/screenshots/getbyidplaintext_endpoint.png" width="600px"</img>
    <p>Delete tip by Id endpoint</p>
    <img src="/screenshots/deletetipbyid_endpoint.png" width="600px"</img>
    <p>Update tip by Id endpoint</p>
    <img src="/screenshots/updatetipbyid_endpoint.png" width="600px"</img>
    <p>Get all tips</p>
    <img src="/screenshots/getall_endpoint.png" width="600px"</img>
    <p>Add new tip</p>
    <img src="/screenshots/addnewtip_endpoint.png" width="600px"</img>
</div>





