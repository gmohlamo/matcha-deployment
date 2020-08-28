# Matcha

A dating site that matches peoples based on a set of criteria

## Requirements

1. Python3
2. pip
3. mysql
  1. mysql root user password issues might occur, need to modify code to comply with user connection credentials
4. virtualenv pip package

### The following is assuming that you are using a Linux or Mac environment to run the project

## Setup

### Download the repository
> git clone github.com/gmohlamo/matcha-development

### Create Python virtual environment
> virtualenv -p python3 matcha/

### Activate virtual environment
> source matcha/bin/activate

### Install program requirements
> pip install -r requirements.txt

### Setup database tables required initially
> python3 setup.py #see Troubleshooting section if this fails.

### Add 500 random user accounts to populate the database
To create 500 dummy user accounts:

### Populate the database with 500 mock users
> mysql -u root -p < populate\_db.sql

## Running

> export FLASK\_APP=run.py

> export FLASK\_ENV=development

> flask run

### Open your web browser on localhost:5000

## Troubleshooting
In the unfortunate event that you receive a "Access denied for user 'root@localhost' error" perform the following:

$ sudo mysql
> use mysql

> update user set plugin='' where user='root';

> flush privileges

> exit or ctrl+D

That should resolve the error.
 
