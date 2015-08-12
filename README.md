![image_squidhome@2x.png](http://i.imgur.com/RIvu9.png)

# Amazon (AWS) Redshift Sails/Waterline Adapter

[![NPM version](https://img.shields.io/npm/v/sails-aws-redshift.svg)](https://www.npmjs.org/package/sails-aws-redshift) [![Dependency Status](https://david-dm.org/wwwslinger/sails-aws-redshift.png)](https://david-dm.org/wwwslinger/sails-aws-redshift)  ![MIT License](http://img.shields.io/badge/license-MIT-green.svg)

A [Waterline](https://github.com/balderdashy/waterline) adapter for [Amazon Redshift](http://aws.amazon.com/redshift/). May be used in a [Sails](https://github.com/balderdashy/sails) app or anything using Waterline for the ORM.

## Motivation

In general, you do not want to use Redshift as your database for typical API or website usage.  Redshift is build for speed on bulk operations, and individual operations on Redshift are relatively slow.  However, if you need a small, internal tool to communicate with Redshift, like an API-based task manager to run large tasks against Redshift, or a small web console to view or work with Redshift data, this will do you just fine.
 
## Install

Install is through NPM.

```bash
$ npm install sails-aws-redshift
```

## Configuration

The following config options are available, with example entries:

```javascript  
config: {  
  database: 'databaseName',  
  host: 'some.cluster.name.us-east-1.redshift.amazonaws.com',  
  user: 'userName',  
  password: 'userPassword',  
  port: 5439,  
  pool: false,  
  ssl: false  
};
```
## Redshift Restrictions

Redshift originally branched from PostgreSQL, but differs quite a bit now.  This adapter version has the following restrictions:  
    1. Redshift is not case-sensitive, so any case sensitivity available with PostreSQL has been removed.  
    2. Redshift does not provide returning statements, so aspects of waterline-sequel which expect this are not available or have been overridden.  
    3. Much syntax in SQL is not supported in Redshift, for example, selecting from table names using "AS <identifier>" in the situation where the real table name is not being used as the identifier.  
    4. Auto-increment is different and currently results in even-numbered primary keys when using this feature.  
    5. Redshift does not support specifying the primary key/id upon creation, so it is good practice to include a separate identifier like a UUID for all models.  
    6. Since returning from a query is not avaialable, the `create` and `update` adapter methods run a subsequent `adapter.find` to get the new/updated object. The create requires that the query appends createdAt and updatedAt values.
## About Waterline

Waterline is a new kind of storage and retrieval engine.  It provides a uniform API for accessing stuff from different kinds of databases, protocols, and 3rd party APIs.  That means you write the same code to get users, whether they live in mySQL, LDAP, MongoDB, or Facebook.

To learn more visit the project on GitHub at [Waterline](https://github.com/balderdashy/waterline).
