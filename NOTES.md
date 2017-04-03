# Notes

## TODO
* Download cobudget ot the aws server
* Check which port Puma is using when in production mode
* Set nginx to redirect to puma

## Relevant environment vars
* DATABASE_URL (“postgres://ud6dfgef6bi48k:pusrad9dnpafvcp9u74ocln6g0@ec2-52-203-250-6.compute-1.amazonaws.com:5432/d1hlu2cr9ta2p3” on Heroku)
	* Format: <adapter>://<host>/<database>
* RAILS_ENV (“production” on Heroku)

## Postgresql instance

To connect using psql: psql -h cobudget1.cnxbxtmxjlog.eu-west-1.rds.amazonaws.com -U chime -d cobudget

### To drop and recreate the database

dropdb -h cobudget1.cnxbxtmxjlog.eu-west-1.rds.amazonaws.com -U chime cobudget 

createdb -h cobudget1.cnxbxtmxjlog.eu-west-1.rds.amazonaws.com -U chime cobudget 

### To load a clean database with data dumped from pg_dump

psql -h cobudget1.cnxbxtmxjlog.eu-west-1.rds.amazonaws.com -U chime -d cobudget < _file_from_previous_pg_dump_

## References
* [Confuguring Ruby on Rails](http://guides.rubyonrails.org/configuring.html)
* [Deploy Ruby On Rails on Ubuntu 16.04 Xenial Xerus - GoRails](https://gorails.com/deploy/ubuntu/16.04))
