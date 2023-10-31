# currencyQuiz
Quiz game for matching a country to its currency!

As of right now, you will need to to do two things to make this app function. The first thing you must do is create a postgres db using the currencies.csv. Then you must make a .env file and put your postgres credentials into the db object. If you have not created a Postgres DB or need assistance on how to create one please follow the directions below.

## Creating your local Postgres DB:

1. To create your Postgres DB you will first need to install Postgres and PG admin. In the installation process for postgres you opt to install pgadmin as well. Make sure to write down the password you make in the installation process!

[postgres](https://www.postgresql.org/download/)

2. Next, open up pgadmin. In the left pane click on "Servers" -> PostGreSQL <version no> -> right click and hover over "create" and then click "Database...".

3. Enter a DB name and click save.

4. Click on your newly created DB. Click on "Query Tool" to the right of Object Explorer. Enter the following code:

```
CREATE TABLE currencies (
	country TEXT,
	currency TEXT,
	code TEXT,
	id SERIAL PRIMARY KEY	
)
```

5. Then click "Execute" (button is in the shape of a right arrow).

6. Next, Expand your database so you can see "Schemas", click on that, scroll down to "Tables" click on this. Then, click on "currencies" table.

7. Right click on "currencies" table. Select "import/export data...".

8. Make sure import is selected, click on the folder icon at the end of the Filename field. Find the path of where the currencies.csv is located. Click on "Options" tab, make sure "Header" is selected. Click OK.

9. Now, make sure to create a .env file inside the root of this project. You will need to have the **USER**, **HOST**, **DATABASE**, **PASSWORD**, **PORT** environment variables defined. These are all pertaining to your Postgres credentials. The default port is **5432**.

10. Congratulations! You created the local Postgres DB! Now you just have to run the project with "node index.js"


