## basic-db
### simple CRUD API to connect to MySQL db

* clone the repository or just the folder `basic-db`

* `cd` to directory

* `pip install -r requirements.txt`
  
* Database Setup
    Flask has support for several relational database management systems, including SQLite, MySQL, and PostgreSQL. MySQL is used for this exercise.
    Along with `Flask-SQLAlchemy` (Python-SQL Object Relational Mapper) and `mysqlclient` (Python 3 interface to MySQL. It will help us connect the MySQL database to the app.)
    
    `mysql -u root`
    
    Once in mysql CLI:
    
      `CREATE USER '{username}'@'localhost or {server IP}' IDENTIFIED BY '{password}';
      
      `CREATE DATABASE somedatabasename;`
      
      `GRANT ALL PRIVILEGES ON somedatabasename . * TO '{username}'@'localhost or {server IP}';`
      
      `ALTER USER '{username}'@'localhost or {server IP}' IDENTIFIED WITH mysql_native_password BY 'youpassword';



* make FLASK_APP variable

    For WindowsOS: `set FLASK_APP=basicapi.py`
  
    For MacOS: `export FLASK_APP=basicapi.py`
   
* Migrations allow us to manage changes we make to the models, and propagate these changes in the database. Python package `flask-migrate`
    
    `flask db init` creates a migrations directory in the project directory
    
    `flask db migrate` creates migration
    
    `flask db upgrade` apply migration

* Set up is all completed
    run `flask run` in terminal at the directory
    
* List of APIs:

      [GET] /delivery                                retrun JSON of all delivery enteries 
      
      [POST] /delivery                               create a delivery entery (fields: businesstype, clientname, order_ID, comment)
      
      [GET] /delivery/<order_id>                     retrun JSON of delivery entry matching `order_id`
      
      [PUT] /delivery/<order_id>                     update delivery entry matching `order_id`
      
      [DELETE] /delivery/<order_id>                  delete delivery entry matching `order_id`
      
      [GET] /shippment                               retrun JSON of all delivery enteries 
      
      [POST] /shippment                              create a delivery entery (fields: ship_ID, contact_info, ship_area, ship_district, driver, car_type, car_ID, is_elevator, floors_byhand, amount_collect, comment)
      
      [GET] /shippment/<ship_id>                     retrun JSON of delivery entry matching `ship_id`
      
      [PUT] /shippment/<ship_id>                     update delivery entry matching `ship_id`
      
      [DELETE] /shippment/<ship_id>                  delete delivery entry matching `ship_id`

References:

* [mbithenzomo](https://github.com/mbithenzomo/project-dream-team-one)

* [MySQLdb User’s Guide](https://mysqlclient.readthedocs.io/user_guide.html#installation)

* [Flask + marshmallow for beautiful APIs](https://flask-marshmallow.readthedocs.io/en/latest/)

* [Flask-SQLAlchemy](http://flask-sqlalchemy.pocoo.org/2.3/quickstart/)
