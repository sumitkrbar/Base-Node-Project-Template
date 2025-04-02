This is a basic node js project template, which anyone can use as it has been prepared, by keeping some of the most important code principles ans project management recommensations. Feel free to change anythig.

`src` → Inside the src folder all the actual source code regarding the project will reside, this will not include any kind of tests. (You might want to make separate tests folder)

Lets take a look inside the `src` folder:

- `config` → In this folder anything and everything regarding any configs or setup of a library or a module will be done. For examples: setting up  `dotenv` so that we can use the environment variables anywhere in a cleaner fashion, this is done in the `server-config.js`. One more example can be to setup you logging library that can help you to prepare meaningful logs, so configurations for this library should also be done here.

- `routes` → In this routes folder, we register a route and the corresponding middleware and controllers to it.

- `middlewares` → They are just going to intercept the incoming requests where we can write our validators, authenticators, etc.

- `controllers` → They are kind of the last middlewares as post them you call your business layer to execute the business logic. In controllers we just receive the incoming requests ans data and then pass it to the business later, and once business layer returns an output, we structure the API response in controllers and send the output.

- `repositories` → This folder contains all the logic using which we interact the DB by writing queries, all the raw queries or ORM queries will  go here.
- `services` → Contains the business logic and interacts with repositores for data from the database.

- `utils` → Contains helper methods, error classes etc.


### Setup the project
- Download the template from github ans open it in your favourite text editor.
- In the root directory create a `.env` file and add the following env variables
   ```
        PORT =<port number of your choice>
   ```
   ex:
   ```
        PORT = 3000
   ```
- Inside the `src/config` folder create a file named as `config.json` ans write the following code: 
    ```
            {
        "development": {
            "username": "root",
            "password": null,
            "database": "database_development",
            "host": "127.0.0.1",
            "dialect": "mysql"
        },
        "test": {
            "username": "root",
            "password": null,
            "database": "database_test",
            "host": "127.0.0.1",
            "dialect": "mysql"
        },
        "production": {
            "username": "root",
            "password": null,
            "database": "database_production",
            "host": "127.0.0.1",
            "dialect": "mysql"
        }
        }
    ```
- If you're setting up your development environement, then write the username of your db, passord of your db and in dialect mention whatever db you are using for ex: mysql, mariadb, etc;
- If you are setting up test or prod environment, make sure you also replace the host with the hosted db url.
