Installation Guide:

Install all necessary python packages.
```
>> pip install -r requirements.txt
```

Make sure postgresql is installed.
```
>> service postgresql status
```

Fill out the postgresql IP and port in webapps/settings.py on line 112 and 113.
```
'HOSY'  : 'localhost'
'PORT'  : '5433' // depends on the postgresql server
```

Add current IP to ALLOWED_HOSTS in webapps/settings.py
```
ALLOWED_HOSTED = [ 'your ip' ]
```

Setup user and database in postgresql: 
```
>> sudo su - postgres
>> psql
>> CREATE USER mapuser
>> CREATE DATABASE mapgether
```

Create Migrations for database
```
>> python manage.py makemigrations mapgether
>> python manage.py migrate
```

Finally, we can run the server now (Note: specify IP and port)
```
>> python manage.py runserver 123.234.123.234:8000
```
