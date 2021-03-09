# Codezvous
*By [Chad Calcote](http://chadcalcote.com/), [Chris Clark](https://percist.github.io/), [Daniel Chin](https://bongochin.github.io/#) - [Live site](https://codezvous.herokuapp.com/)*

A Meetup clone designed for fellow programmers to meet other tech-minded individuals within groups and at events in their area.

You can also visit Meetup [here](https://www.meetup.com/home/).

For a deeper dive into our planning process and code setup, please visit our [Wiki](https://github.com/ChadCalcote/Codezvous/wiki)!

**Table of Contents**
  * [Codezvous at a Glance](#Codezvous-at-a-glance)
  * [Technologies Used](#technologies-used)
  * [Application Architecture](#application-architecture)
  * [Frontend Overview](#frontend-overview)
  * [Backend Overview](#backend-overview)
  * [Conclusion](#conclusion)

## Codezvous at a Glance
Codezvous is a Meetup clone designed for fellow programmers to meet other tech-minded individuals within groups and at events in their area.

The application is made with a React frontend utilizing original components.
The backend is a Python Flask server with a PostgreSQL database.

**Key Features**
* User sign in / sign up with flask-login authentication and encrypted password with werkzeug
* View, create, and join tech groups in your area
* View, create, and RSVP for events of the groups you are a part of
* Comment and see other comments on events
<!--
![CoffeeHub mini-demo](/readme-assets/star-trader-demo-full.gif) -->

## Technologies Used
* Frontend
  * React
  * Javascript
  * Redux
  * CSS
* Backend
  * Flask
  * Python
  * Postgres
  * SQLAlchemy
  * Alembic
  * Heroku deployment via Docker

## Application Architecture
The frontend is a `create-react-app` using functional components with hooks. The backend is a Flask server with various RESTful endpoints. They are deployed via Docker to a Heroku server.

##### Codezvous Postgres database schema
Schema Photo


## Frontend Overview
The front end is is modeled after Meetup and uses all original styling. We implemented a custom component library for all events, groups, and users to keep styling the same and DRY up the code base.

Code Snippet Description Here:

Code Snippet Photos
Code Snippet Photos

## Backend Overview
The Flask backend is a collection of RESTful routes serving data to the frontend and an interface with the Postgres database.

The database is queried using the SQLAlchemy ORM, and seed data was created using the faker packing and added using the Alembic library.

## Backend Installation and Setup

1. Clone this repository (only this branch)

   ```bash
   git clone https://github.com/appacademy-starters/python-project-starter.git
   ```

2. Install dependencies

      ```bash
      pipenv install --dev -r dev-requirements.txt && pipenv install -r requirements.txt
      ```

3. Create a **.env** file based on the .env.example with proper settings for your
   development environment

4. Setup your PostgreSQL user, password and database and make sure it matches your **.env** file

5. Get into your pipenv, migrate your database, seed your database, and run your flask app

   ```bash
   pipenv shell
   ```

   ```bash
   flask db upgrade
   ```

   ```bash
   flask seed all
   ```

   ```bash
   flask run
   ```

6. To run the React App in development, checkout the [README](./react-app/README.md) inside the `react-app` directory.

***
*IMPORTANT!*
   If you add any python dependencies to your pipfiles, you'll need to regenerate your requirements.txt before deployment.
   You can do this by running:

   ```bash
   pipenv lock -r > requirements.txt
   ```

*ALSO IMPORTANT!*
   psycopg2-binary MUST remain a dev dependency because you can't install it on apline-linux.
   There is a layer in the Dockerfile that will install psycopg2 (not binary) for us.
***


## Conclusion
Codezvous was our idea as a team to create a Meetup clone that was more niche. As outgoing developers who have been bogged down behind our desks and writing endless lines of code, we wanted to create a platform for individuals like ourselves to meet other engineers in their area, network, and talk about code, all coming together for the common goal to strengthen technology in your community. 

Future features would include a search bar to find events and groups, categories to isolate events or groups, and a calendar feature to keep you and your groups' events organized.
