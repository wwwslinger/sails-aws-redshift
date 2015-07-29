![image_squidhome@2x.png](http://i.imgur.com/RIvu9.png)

# Amazon (AWS) Redshift Sails/Waterline Adapter

[![Build Status](https://travis-ci.org/wwwslinger/sails-aws-redshift.png?branch=master)](https://travis-ci.org/wwwslinger/sails-aws-redshift) [![NPM version](https://badge.fury.io/js/sails-aws-redshift.png)](http://badge.fury.io/js/sails-aws-redshift) [![Dependency Status](https://gemnasium.com/wwwslinger/sails-aws-redshift.png)](https://gemnasium.com/wwwslinger/sails-aws-redshift)

A [Waterline](https://github.com/balderdashy/waterline) adapter for [Amazon Redshift](http://aws.amazon.com/redshift/). May be used in a [Sails](https://github.com/balderdashy/sails) app or anything using Waterline for the ORM.

## Install

Install is through NPM.

```bash
$ npm install sails-aws-redshift
```

## Configuration

The following config options are available along with their default values:

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

## About Waterline

Waterline is a new kind of storage and retrieval engine.  It provides a uniform API for accessing stuff from different kinds of databases, protocols, and 3rd party APIs.  That means you write the same code to get users, whether they live in mySQL, LDAP, MongoDB, or Facebook.

To learn more visit the project on GitHub at [Waterline](https://github.com/balderdashy/waterline).
