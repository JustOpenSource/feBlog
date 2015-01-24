# feBlog
Fatal Encounters Blog

## Setup

### Install requirements

First, install mezzanine globally or in your virtual environment.

	$ pip install mezzanine

### Clone project

	$ cd developmentDirectory
	$ git clone https://github.com/JustOpenSource/feBlog.git
	$ cd feBlog/feBlog

### Create local settings

Create a local_settings.py file at develomentDirectory/feBlog/feBlog/local_settings.py, a sibling of settings.py*

	$ touch local_settings.py

In local_settings.py, add the following (change the secret key to a generated [random string](http://www.unit-conversion.info/texttools/random-string-generator/)).

	DEBUG = True

	# Make these unique, and don't share it with anybody.
	SECRET_KEY = "randomstring"
	NEVERCACHE_KEY = "randomstring"

	DATABASES = {
	    "default": {
	        # Ends with "postgresql_psycopg2", "mysql", "sqlite3" or "oracle".
	        "ENGINE": "django.db.backends.sqlite3",
	        # DB name or path to database file if using sqlite3.
	        "NAME": "dev.db",
	        # Not used with sqlite3.
	        "USER": "",
	        # Not used with sqlite3.
	        "PASSWORD": "",
	        # Set to empty string for localhost. Not used with sqlite3.
	        "HOST": "",
	        # Set to empty string for default. Not used with sqlite3.
	        "PORT": "",
	    }
	}

### Create a local development database

	$ python manage.py createdb --noinput

### Run your server

	$ python manage.py runserver

This should let you see the website at [localhost:8000](localhost:8000)