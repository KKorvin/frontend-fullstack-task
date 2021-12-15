# Naviteq Task for Senior Fullstack Developer

The goal is to create a simple web app which determines gender of given name and stores usage statistics. Based on https://genderize.io/

The app should consist of the following parts:

## App structure

3 URLs:

1. `/` (home page) - simple form where you can enter the name and receive its gender.
2. `/statistics` - will show statistics of app usage: how many names were determined, what percent of names were male and what female, what is the most popular name.
3. `/api/names` - Private API endpoint, which returns JSON with all names and genders in app database. Should have some kind of authentication by API key.

* Please develop frontend with one of these frameworks: Angular, React, Vue.js

## Backend

Backend which useses the https://genderize.io/ API to determine names and stores the results in the database so we will not need to call genderize API twice for the same name. Backend should also include the unit tests.

Please develop backend as API endpoints which will bee used by framework you choose for frontend.

## Docker

Use Docker Compose for defining containers for your application. It should be possible to run `docker compose up`, navigate to `localhost:8080` and view the app running.

## Technology stack

Feel free to use your favorite technology stack.

-----

## Application details

### Stack

* Mongo DB 
* React.js
* Node.js (Express)
* Docker

### HOW TO USE THE APP

Start: `docker compose up`

UI app is served on `http://localhost:8080`
API is served on `http://localhost:5000/api`

Testing UI: `docker build -t node-docker --target test ./backend` 
Testing API: `docker build -t node-docker --target test ./frontend`

OR: `yarn run test` in the corresponding directories

#### API keys:
The system stores hashed versions of API keys, not the keys itself.
Two initial test hashes are injected via `docker-compose`.

Valid keys to check:
`http://localhost:5000/api/names?apiKey=ee8f9fb4f5c35c3aec95107a05bebc82`
`http://localhost:5000/api/names?apiKey=b0dc2725d3b61ead193753b5f07c687c`
