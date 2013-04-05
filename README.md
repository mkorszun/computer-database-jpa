###This is a classic CRUD application, backed by a JDBC database. It demonstrates:

- Accessing a JDBC database, using JPA.
- Achieving, table pagination and CRUD forms.
- Integrating with a CSS framework (Twitter Bootstrap ).

Twitter Bootstrap requires a different form layout to the default one that the Play 2.0 form helper generates, so this application also provides an example of integrating a custom form input constructor.

###To deploy on [cloudControl](https://www.cloudcontrol.com/) using different data storages:

#### H2 DB (built-in)

Clone repository:

~~~bash
$ git clone https://github.com/mkorszun/computer-database-jpa.git playexample ; cd playexample
~~~

Create application with custom buildpack:

~~~bash
$ cctrlapp playexample create custom --buildpack https://github.com/cloudControl/heroku-buildpack-scala
~~~

Push:

~~~bash
$ cctrlapp playexample/default push
~~~

Deploy:

~~~bash
$ cctrlapp playexample/default deploy
~~~

Test it: 
######http://playexample.cloudcontrolled.com

#### Elephantsql/PostgreSQL

Checkout elephantsql branch (check commit log for required modifications):

~~~bash
$ git checkout elephantsql
~~~

Push:

~~~bash
$ cctrlapp playexample/elephantsql push
~~~

Create [Elephantsql](https://www.cloudcontrol.com/add-ons/elephantsql) addon:

~~~bash
$ cctrlapp playexample/elephantsql addon.add elephantsql.turtle
~~~

Deploy:

~~~bash
$ cctrlapp playexample/elephantsql deploy
~~~

Test it:

######http://elephantsql.playexample.cloudcontrolled.com/

#### MySQLs

Checkout mysqls branch (check commit log for required modifications):

~~~bash
$ git checkout mysqls
~~~

Push:

~~~bash
$ cctrlapp playexample/mysqls push
~~~

Create [MySQLs](https://www.cloudcontrol.com/add-ons/mysqls) addon:

~~~bash
$ cctrlapp playexample/mysqls addon.add mysqls.free
~~~

Deploy:

~~~bash
$ cctrlapp playexample/mysqls deploy
~~~

Test it:

######http://mysqls.playexample.cloudcontrolled.com/