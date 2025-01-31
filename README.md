# couchdb-to-mongodb
This repository consists of scripts which can help migrating data from your couchdb databases to mongodb collections

## Dependency
These are the dependency libraries/packages which has been used for the scripts which has been used for migration scripts : 

Library/Package Name | Description | Web Reference
---------------------|-------------|--------------
Node.js 6.x | Node.js framework is necessary to run node scripts | [install/download](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server)
Couchbackup | Npm package to install | [install](https://www.npmjs.com/package/@cloudant/couchbackup)
MongoDB 3.4 | Mongodb where restore will happen :p | [install](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)

## Pre-Requisite
As these scripts are shell scripts you will need to export variables to your linux shells, you may want to save these in your profile rc file as well : 

`export COUCH_URL="https://username:password@hostname:port"`

`export COUCH_BUFFER_SIZE=10000`

`export LC_ALL=C`

### For IBM Cloudant database
As per resolution of [issue](https://github.com/jimishio/couchdb-to-mongodb/issues/1), IBM Cloudant databases can be migrated easily to mognoDB as well. All the cloudant users can use below `COUCH_URL` env variable : 

`export COUCH_URL="https://MY_USERNAME:MY_PASSWORD@MY_ACCOUNT@cloudant.com:port"`

## Run Script
Finally all you need is database name of couchdb, mongodb database name & credentials. Run following script with following command : 

`master_script.sh collection_name mongo_db_name mongo_username mongo_password mongo_host mongo_port`

For users, who are having mongodb open (I mean without user authentication), they can use another script and hit this command : 

`./master_script_without_pwd.sh collection_name mongo_db_name mongo_host mongo_port`

Happy Coding!
-@jimishio
