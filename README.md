# Theatre api service


This is an API for a theater website. Using this API, you can create a website where you can view upcoming performances, their genres, and the actors who play in these performances. View available seats in the theater hall and create orders with tickets. 

The API has the following database structure:

![Database structure](theatre_db_structure.png)

## You can get the API from Docker

```shell
docker https://github.com/nazar-dmytrenko/Theatre-API-Service

```

## Installation

Python3 must be already installed!

You also need to install PostgreSQL and create a database.

```shell
git clone https://github.com/nazar-dmytrenko/Theatre-API-Service
cd theatre_api_service
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
touch .env
```
For Windows, the command "touch .env" will be "echo > .env"

For an example of filling out .env, see .env.sample!
```shell
python manage.py migrate
python manage.py runserver
```

## Build the Docker images

Docker must be already installed!


```shell
docker-compose build
```
Run the Docker containers:
```shell
docker-compose up
```

The API should now be accessible at http://localhost:8001/

### Getting access

You can create superuser:

```shell
python manage.py createsuperuser
```
or create a default user using the following links

`http://127.0.0.1:8000/api/user/register/`

To work with token use:

- get access token and refresh token http://127.0.0.1:8000/api/user/token/
- refresh access token http://127.0.0.1:8000/api/user/token/refresh/
- verify access token http://127.0.0.1:8000/api/user/token/verify/

#### Note: Make sure to send Token in api urls in Headers as follows

- key: Authorization

- value: Bearer `<token>`


## Features:


- JWT authenticated:
- Admin panel: /admin/
- Documentation is located at: </api/doc/swagger/>, </api/doc/redoc/>
- Managing reservations and tickets
- Creating plays with genres and actors
- Creating theatre halls
- Creating performances with show time, play and theatre hall
- Filtering plays and performances