# Today we looked at databases, how to set up one, and how to use it in an app like Sinatra. You can follow the steps below to practice your understanding of databases.

# REMEMBER TO TDD!

1. First, ensure you have the postgres client installed on your machine. You can confirm this by typing `brew install postgresql` 

2. Create a Postgres data source in Heroku. Using either  [Postico](https://eggerapps.at/postico/) or [PGAdmin](https://www.pgadmin.org/),ensure you can connect to your database server

3. Using the list of pets in the google doc, create a pets table. How many columns do you need, and what field types should they be?

4. Add 3 pets into the table. Using SQL (you may need to dig around for this), write and execute 2 statements. One should return the number of pets in the table, and the other should return just the name of the pets in the table.

5. Add the `pg` gem to your existing sinatra project, and create an endpoint that, when called, will return the number of pets in your table. Create a separate one that will return the owners of the pets in the table.


The next set of tasks might be more challenging, so you can return to them at a later time if you want.

- Looking at the pets table, what duplication, if any do you notice? With relational databases we want to avoid duplication of info where possible. You may notice for example, the same owners of pets repeat. 

Create another table called owners and add their names there. Change the pets table so that instead of writing the name of the owner, you write the id of the owner. Run a query to list all the pets in the table and note any changes  you see.

- Create another endpoint (or edit an existing one) so that hitting it will list the pets and their respective owners.

- You may wonder why you see a number rather than a name-it's because we've moved that information into a separate table and are referencing it using the id. We can access it by using a `join` statement. See if you can use this so that you can return the name of the owner, not just the id.

- At this point you might find it challenging to move between SQL and Ruby. One of the features of rails is its ActiveRecord, which makes it easier to think more about objects than SQL statements. Similar frameworks are [Sequel](https://sequel.jeremyevans.net/) and [Ruby Object Mapper](https://rom-rb.org/learn/core/5.2/quick-setup/). Try using either and see if it is easier to retrieve the data you want to display. *If successful*, there's still some duplication in the pets table-create another table, and ensure your endpoint of listing all the pets and their owner work. Did you find it easier to work with SQL or with an ORM?

- Instead of manually entering pets into the table, create an endpoint that allows you to pass in that information.