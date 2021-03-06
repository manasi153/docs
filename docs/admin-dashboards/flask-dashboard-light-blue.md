title: Flask Dashboard Light Blue

# [Flask Dashboard Light Blue](https://appseed.us/admin-dashboards/flask-dashboard-light-blue)

**Open-Source Admin Dashboard** coded in **[Flask Framework](https://palletsprojects.com/p/flask/)** on top of **Light Blue Dashboard** design (free version) - Provided by **AppSeed** [Web App Generator](https://appseed.us/app-generator).

## Dashboard Features
---

- SQLite, PostgreSQL, SQLAlchemy ORM
- Alembic (DB schema migrations)
- Modular design with **Blueprints**
- Session-Based authentication (via **flask_login**), Forms validation
- Deployment scripts: Docker, Gunicorn / Nginx
- UI Kit: **[Light Blue Dashboard](https://flask-dashboard-light-blue.appseed.us/login)** (Free version) provided by **FlatLogin**
- **MIT License**
- Support: Free support via **Github** and (Paid) **24/7 LIVE Support** via [Discord](https://discord.gg/fZC6hup)

<br />

## Dashboard technology stack
---

- Used Language: [Python3](https://www.python.org/) (Python2 is not supported)
- Web Framework: [Flask](https://www.palletsprojects.com/p/flask/)
- CSS Framework: [Bootstrap CSS](https://getbootstrap.com/)
- Javascript: [jQuery](https://jquery.com/)

<br />

## Dashboard Links
---

- [Flask Dashboard Light Blue](https://appseed.us/admin-dashboards/flask-dashboard-light-blue) - Product page
- [Flask Dashboard Light Blue](https://docs.appseed.us/admin-dashboards/flask-dashboard-light-blue/) - Documentation
- [Flask Dashboard Light Blue](https://flask-dashboard-light-blue.appseed.us/login) - LIVE Demo

<br />

![Flask Dashboard Light Blue - Open-Source Admin Panel.](https://raw.githubusercontent.com/app-generator/static/master/products/flask-dashboard-light-blue-screen.png)

<br />

## Prepare your environment
---

The product is built on top of [Flask](https://palletsprojects.com/p/flask/), a popular Python Web Framework. To build the app, Python3 should be installed properly in the workstation. If you are not sure if Python is properly installed, please open a terminal and type `python --version`. The full-list with dependencies and tools required to build the app:

- [Python3](https://www.python.org/) - the programming language used to code the app
- [Git](https://git-scm.com/) - used to clone the source code from the Github repository
- A [Github](https://github.com/) account - the invitation to the source code, will be sent on your account.
- Basic development tools (g++ compiler, python development libraries ..etc) used by Python to compile the app dependencies in your environment.

<br />

> Check Python (using the terminal)

```bash
$ # Check Python version
$ python --version
Python 3.7.2 # <--- All good
```

<br />

> Check GIT command tool (using the terminal)

```bash
$ # Check git
$ git --version
$ git version 2.10.1.windows.1 # <--- All good
```

<br />

For more information on how to set up your environment please access the resources listed below. In case we've missed something, contact us on Discord.

- [How to set up Python](/how-to/install-python)
- [Setup CentOS for development](/how-to/setup-centos-for-development/)
- [Setup Ubuntu for development](/how-to/setup-ubuntu-for-development/)
- [Setup Windows for development](/how-to/setup-windows-for-development/)

<br />

## Project Structure
---

The boilerplate code is built with a modular structure that follows the recommended pattern used by many open-source projects. The most important files and  directories are shown below:

<br />

```bash
< PROJECT ROOT >                          # application root folder
    |
    |--- app/__init__.py                  # application constructor  
    |--- app/base/                        # base blueprint
    |--- app/base/static/assets           # Img, CSS, Janascript files
    |--- app/base/templates               # Jinja2 files (layouts, login pages)
    |                |---<errors>         # Dir with Error pages: 404, 500
    |                |---<login>          # Dir with Login and Registration pages
    |                |---<site_template>  # Dir with Login and Registration pages
    |
    |
    |--- app/home/                        # home blueprint
    |--- app/home/templates               # Jinja2 files (Pages): index, icons, tables
    |                |---- index.html     # Main dashboard page
    |                |---- maps.html      # Maps page
    |                |---- chats.html     # Charts Page
    |                |---- tables.html    # UI Tables
    |                |---- icons.html     # Ui Icons
    |
    |--- .env                             # store env variables
    |--- config.py                        # app configuration profiles: Debug, Production
    |
    |--- requirements.txt                 # Requirements for production PostgreSQL BDMS
    |--- requirements-sqlite.txt          # Requirements for development - SQLite storage
    |
    |--- run.py                           # bootstrap the app
    |
    |-----------------------------
```

<br />

## Build from sources
---

```bash
$ # Get the code
$ git clone https://github.com/app-generator/flask-dashboard-light-blue.git
$ cd flask-dashboard-light-blue
$
$ # Virtualenv modules installation (Unix based systems)
$ virtualenv --no-site-packages env
$ source env/bin/activate
$
$ # Virtualenv modules installation (Windows based systems)
$ # virtualenv --no-site-packages env
$ # .\env\Scripts\activate
$
$ # Install modules
$ # SQLIte version (no PostgreSQL)
$ pip3 install -r requirements-sqlite.txt
$
$ # OR with PostgreSQL connector
$ pip install -r requirements.txt
$
$ # Set the FLASK_APP environment variable
$ (Unix/Mac) export FLASK_APP=run.py
$ (Windows) set FLASK_APP=run.py
$ (Powershell) $env:FLASK_APP = ".\run.py"
$
$ # Set up the DEBUG environment
$ # (Unix/Mac) export FLASK_ENV=development
$ # (Windows) set FLASK_ENV=development
$ # (Powershell) $env:FLASK_ENV = "development"
$
$ # Start the application (development mode)
$ # --host=0.0.0.0 - expose the app on all network interfaces (default 127.0.0.1)
$ # --port=5000    - specify the app port (default 5000)  
$ flask run --host=0.0.0.0 --port=5000
$
$ # Access the dashboard in browser: http://127.0.0.1:5000/
```

<br />

## Deployment

The app is provided with a basic configuration to be executed in [Docker](https://www.docker.com/), [Gunicorn](https://gunicorn.org/), and [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/).

<br />

### [Docker](https://www.docker.com/) execution
---

The application can be easily executed in a docker container. The steps:

> Get the code

```bash
$ git clone https://github.com/app-generator/flask-dashboard-light-blue.git
$ cd flask-dashboard-light-blue
```

> Start the app in Docker

```bash
$ sudo docker-compose pull && sudo docker-compose build && sudo docker-compose up -d
```

Visit `http://localhost:5005` in your browser. The app should be up & running.

<br />

### [Gunicorn](https://gunicorn.org/)
---

Gunicorn 'Green Unicorn' is a Python WSGI HTTP Server for UNIX.

> Install using pip

```bash
$ pip install gunicorn
```
> Start the app using `gunicorn` binary

```bash
$ gunicorn --bind 0.0.0.0:8001 run:app
Serving on http://localhost:8001
```

Visit `http://localhost:8001` in your browser. The app should be up & running.

<br />

### [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/)
---

Waitress (Gunicorn equivalent for Windows) is meant to be a production-quality pure-Python WSGI server with very acceptable performance. It has no dependencies except ones that live in the Python standard library.

> Install using pip

```bash
$ pip install waitress
```
> Start the app using [waitress-serve](https://docs.pylonsproject.org/projects/waitress/en/stable/runner.html)

```bash
$ waitress-serve --port=8001 run:app
Serving on http://localhost:8001
```

Visit `http://localhost:8001` in your browser. The app should be up & running.

<br />

<br />

## Flask Dashboard Light Blue - app screens
---

<br />

![Flask Dashboard Light Blue - UI Notifications Page.](https://raw.githubusercontent.com/app-generator/static/master/products/flask-dashboard-light-blue-screen-1.png)

<br />

![Flask Dashboard Light Blue - UI Typography Page.](https://raw.githubusercontent.com/app-generator/static/master/products/flask-dashboard-light-blue-screen-2.png)

<br />

![Flask Dashboard Light Blue - User Profile Page.](https://raw.githubusercontent.com/app-generator/static/master/products/flask-dashboard-light-blue-screen-3.png)

<br />

## Credits & Links
---

<br />

## What is [Flask](https://www.palletsprojects.com/p/flask/)

[Flask](https://www.palletsprojects.com/p/flask/) is a lightweight WSGI web application framework. It is designed to make getting started quick and easy, with the ability to scale up to complex applications. It began as a simple wrapper around Werkzeug and Jinja and has become one of the most popular Python web application frameworks.

<br />

## [What is dashboard](https://en.wikipedia.org/wiki/Dashboard_(business))

In information technology, a **[dashboard](https://en.wikipedia.org/wiki/Dashboard_(business))** is a user interface that, somewhat resembling an automobile's dashboard, organizes and presents information in a way that is easy to read. However, a computer dashboard is more likely to be interactive than an automobile dashboard (unless it is also computer-based). To some extent, most graphical user interfaces (GUIs) resemble a dashboard - by [Techtarget](https://searchcio.techtarget.com/definition/dashboard)

<br />

## [Light Blue Dashboard](https://github.com/flatlogic/light-blue-dashboard)

Using this template you will be able to leverage lots of built-in components and thus focus on building features that set you apart from competitors rather than bulding everything from scratch - provided by **[FlatLogic](https://flatlogic.com/)**.

<br />

---
[Flask Dashboard Light Blue](https://appseed.us/admin-dashboards/flask-dashboard-light-blue) - Provided by **AppSeed** [Web App Generator](https://appseed.us/app-generator).
