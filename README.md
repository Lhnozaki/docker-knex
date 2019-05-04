### Start the database

**Ensure that your .env is setup with the correct values**

Then run the following command in the same folder as the docker-compose file:  
`docker-compose up`


## Creating a knexfile

The settings used by knex to talk to a database must file be defined in knexfile.js.
But first we need to instal the knex cli:

`npm i -g knex`

Once the cli is installed, create the knexfile.js file by typing this into the terminal while in the project root:

`knex init`

Modify `knexfile.js` to look like the one in this repo. You'll notice that a lib called `dotenv` is used. This library allows the usage of the key/value pairs in the `.env` to be used on node through `process.env`.

Install `dotenv` using this command:

`npm i dotenv`

Now the value in the .env file will also be used by knex whenever it needs to connect to the database.


### Creating knex migrations

`knex migrate:make ${name_of_migration}`

This is generate a `migrations` directory from the project root and create your first migration file. Edit this file to your needs.


### Running knex migrations

Migrations can be run from the command line using:

`knex migrate:latest`

Migrations can be rolled back using:

`knex migrate:rollback`


### Creating Seed files

`knex seed:make ${name_of_seed_file}`

This is generate a `seeds` directory from the project root and create your first seed file. Edit this file to your needs.


### Running knex seeds

Seed files can be run from the command line using:

`knex seed:run`

Seeds can be rolled back using:

`knex migrate:rollback`
