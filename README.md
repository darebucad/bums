# Basic User Management System (BUMS)

A basic system for implementing authentication (login page) and CRUD principles, allowing admin t add a new user, 
edit, delete (note: multiple) and view a list of all users.


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to install the software and how to install them

Apache and Mysql e.g. xampp-windows-x64-7.3.9-0-VC15, laragon
Composer
Node.js


### Installing

Clone the repository

    $ git clone git@github.com:darebucad/bums.git

Switch to the repo folder

    $ cd bums

Install dependencies

    $ composer install

Compile all necessary scripts

    $ npm run dev

Run the database migrations (**Set the database connection in .env before migrating**)

    php artisan migrate

Start the local development server

    php artisan serve

You can now access the server at http://localhost:8000 (or you can configure your apache server to set the document root into [project folder]/public)

## Running the tests

I have installed vue devtools in my browser, in this tool I have managed to see inputs in my vue form.



