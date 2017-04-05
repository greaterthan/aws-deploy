# Notes

## TODO
* Load the frontend on the site as well

## SSH config

For the AWS instance running the cobudget backend

```
Host cobudget
	Hostname 52.31.141.254
	User ubuntu
```

## Relevant environment vars

 The database url format is postgres://username:password@localhost/myrailsdb

* DATABASE_URL (`postgres://ud6dfgef6bi48k:pusrad9dnpafvcp9u74ocln6g0@ec2-52-203-250-6.compute-1.amazonaws.com:5432/d1hlu2cr9ta2p3` on Heroku)
	* Format: `<adapter>://<host>/<database>`
* RAILS_ENV (`production` on Heroku)
* RACK_ENV (`production` on Heroku)
* PORT - the port Puma connect to (will be set on Heroku at puma start)
* SECRET_KEY_BASE - 

## Postgresql instance

To connect using psql: `psql -h cobudget1.cnxbxtmxjlog.eu-west-1.rds.amazonaws.com -U chime -d cobudget`

### To drop and recreate the database

`dropdb -h cobudget1.cnxbxtmxjlog.eu-west-1.rds.amazonaws.com -U chime cobudget`

`createdb -h cobudget1.cnxbxtmxjlog.eu-west-1.rds.amazonaws.com -U chime cobudget`

### To load a clean database with data dumped from pg_dump

`psql -h cobudget1.cnxbxtmxjlog.eu-west-1.rds.amazonaws.com -U chime -d cobudget < <file_from_previous_pg_dump>`

## Starting cobudget

Make sure all packages are installed `bundle install`

Set environment vars: `. ./env`
Start: `/bin/rails s`

## Extra installs

`sudo apt-get install postgresql-common libpq-dev`

## References
* [Confuguring Ruby on Rails](http://guides.rubyonrails.org/configuring.html)
* [Deploy Ruby On Rails on Ubuntu 16.04 Xenial Xerus - GoRails](https://gorails.com/deploy/ubuntu/16.04)
* [Rails Deployment Tutorial](https://www.ralfebert.de/tutorials/rails-deployment/)
