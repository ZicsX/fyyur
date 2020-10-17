Fyyur
-----

## Introduction

Fyyur is a musical venue and artist booking site that facilitates the discovery and bookings of shows between local performing artists and venues. This site lets you list new artists and venues, discover them, and list shows with artists as a venue owner.

Your job is to build out the data models to power the API endpoints for the Fyyur site by connecting to a PostgreSQL database for storing, querying, and creating information about artists and venues on Fyyur.

### Backend Dependencies
Our tech stack will include the following:
 * **virtualenv** as a tool to create isolated Python environments
 * **SQLAlchemy ORM** to be our ORM library of choice
 * **PostgreSQL** as our database of choice
 * **Python3** and **Flask** as our server language and server framework
 * **Flask-Migrate** for creating and running schema migrations
You can download and install the dependencies mentioned above using `pip` as:
```
pip install virtualenv
pip install SQLAlchemy
pip install postgres
pip install Flask
pip install Flask-Migrate
pip install Flask-Script
pip install psycopg2

```
> **Note** - If we do not mention the specific version of a package, then the default latest stable package will be installed. 

### Frontend Dependencies
You must have the **HTML**, **CSS**, and **Javascript** with [Bootstrap 3](https://getbootstrap.com/docs/3.4/customize/) for our website's frontend. Bootstrap can only be installed by Node Package Manager (NPM). Therefore, if not already, download and install the [Node.js](https://nodejs.org/en/download/). Windows users must run the executable as an Administrator, and restart the computer after installation. After successfully installing the Node, verify the installation as shown below.
```
node -v
npm -v
```
Install [Bootstrap 3](https://getbootstrap.com/docs/3.3/getting-started/) for the website's frontend:
```
npm init -y
npm install bootstrap@3
```


## Main Files: Project Structure
  ```sh
  
  ├── README.md
  ├── app.py *** the main driver of the app."python app.py" to run after installing
  ├── models.py *** Includes your SQLAlchemy models.
  ├── config.py *** Database URLs, CSRF generation, etc
  ├── error.log
  ├── forms.py *** Your forms
  ├── manage.py *** database migrations for Flask applications using Alembic
  ├── requirements.txt *** The dependencies we need to install with "pip3 install -r requirements.txt"
  ├───static
  │   ├───css
  │   ├───fonts
  │   ├───ico
  │   ├───img
  │   └───js
  │       └───libs
  ├───templates
  │   ├───errors
  │   ├───forms
  │   ├───layouts
  │   └───pages
  
  ```
Overall:
* Models are located in the `MODELS` section of `models.py`.
* Controllers are located in `app.py`.
* The web frontend is located in `templates/`, which builds static assets deployed to the web server at `static/`.
* Web forms for creating data are located in `form.py`

## Development Setup
**Initialize and activate a virtualenv using:**
```
python -m virtualenv env
source env/bin/activate
```
>**Note** - In Windows, the `env` does not have a `bin` directory. Therefore, you'd use the analogous command shown below:
```
env/Scripts/activate
```

**Install the dependencies:**
```
pip install -r requirements.txt
```

**Run the development server:**
*Run flask_migrate:* - for creating and running schema migrations

```
python3 manage.py db init
python3 manage.py db migrate
python3 manage.py db upgrade
```
```
export FLASK_APP=myapp
export FLASK_ENV=development # enables debug mode
python3 app.py
```

**Verify on the Browser**
Navigate to project homepage [http://127.0.0.1:5000/](http://127.0.0.1:5000/) or [http://localhost:5000](http://localhost:5000)