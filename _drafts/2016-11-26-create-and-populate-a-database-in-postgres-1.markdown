---
layout: post
title:  "Using Postgres: Creating and Populating a Database — A Friendly Tutorial"
date:   2016-11-26 17:51:55 -0800
categories: sql tutorial
---

## Getting Postgres Installed and Set Up

Okay, you decided to learn SQL. More than just learning SQL, you’ve decided to learn Postgres. Good for you! Postgres is amazing and it’s pretty commonly used out there in the real world, so I want to congratulate you on making the right choice.

Let’s dive right in. There are a number of different ways to do this, but I recommend downloading and installing the [happy little elephant icon installation][postgres-app]. That will spin up your PSQL server.

There are tons of ways to do things and tons of opinions as to which is better, and far be it for me to say that this path is somehow better than another's. That said, in this tutorial we're going to take the easy road, but you can do whatever you want… I won’t judge :)

Now after you’ve installed Postgres, fire up your terminal and pop into Postgres by typing ```psql``` on the command line.

When you do that you should see a Postgres version number at the top and a friendly reminder that you can type help for… You guessed it… help!

```
psql (9.6.1)
Type "help" for help.
```

You should also see a command line with your username and the ```#```. This is where you’re going to enter your SQL commands. In my case my username is labyrinth, so in my examples you are to see my username being used just like this:

```
labyrinth-#
```
## Creating a New Database

Now that we're inside our Postgres command line, we need to actually create a database. You see, the database is where we put all our tables, and our tables is where we put all our data. You can think of the Postgres database as a filing cabinet (**database**), and the filing cabinet is filled with printed out spreadsheets (**tables**).

For our example, we are going to create a new **database** which stores a list of the best video games of all times which I have unceremoniously selected from my personal preferences. Once we fill this new video game database with information, we will be able to manipulate it and see all the nifty ways that Postgres can play with our data to give us specific results! 

To create the database we simply use the ```CREATE DATABASE``` command as seen below. We will then see the output of the command on the next line. In this case ```CREATE DATABASE```

```
labyrinth=# CREATE DATABASE video_games;
CREATE DATABASE
```

Now we need to connect to our database from inside of Postgres. We do this typing ```\connect video_games```. 

```
labyrinth=# \connect video_games
You are now connected to database "video_games" as user "labyrinth".
```

Hooray! We're connected! 🎉


## Creating a Table in Our Database

Okay great! Now that we have our database set up, we will have to create a **table** *in* the database on which we will store our information (Remember you can imagine this as a file in the filing cabinet).

Let’s create a table that’s going to hold all our games. We will call it ```games```. I know, The title may not seem like it's particularly clever, but when you're creating tables, you want the names to be as plainly descriptive as possible. ```happy``` is not a particularly useful name for a table unless you're actually saving something for which happiness has a meaningful, primary and specific descriptor of the data itself.

When we create the table we have to specify what sort of information each **column** in the table is going to hold. For our purposes, we will use a couple of different columns (Remember, you can think of these as a column on a spreadsheet). We will have a column for the name, release date, game publisher and purchase price of each game.

![SQL table model]({{ site.url }}/assets/sql_tutorial_table.png)

When creating column names, avoid using spaces between multiple words such as in the release date column listed above. 



One last thing before we create our table, we need to know how to setup the table's primary key.


### 🔑 Setting up a Primary Key (*What is a primary key?*)


A **primary key** is what uniquely identifies each row in our table– This makes it easy for us to go back and update or delete specific rows in the table if we want to do so.

A primary key is (for our purposes) basically a number that’s associated with each new entry in our table. Our primary key will be an integer and it will increment up by 1 with each new entry into the table. Basically just keep in mind this is a unique way to identify each record in the table. It will happen automatically once you create it initially. You don’t have to fuss with it and in truth, you really shouldn’t.

### Okay, let's create a table!

The following command will create our table (don't worry, it will be explained in detail below):

```
video_games=# CREATE TABLE games (
id SERIAL PRIMARY KEY,
name text NOT NULL,
release_date DATE NOT NULL,                                                                                                 
publisher TEXT NOT NULL
);
```

The primary element that's required in actually *running* the SQL statement is the `;` at the end of the whole statement. Without this, the statement will not run!

Now let's breakdown the SQL statement above so we can get a better understanding of how Postgres is creating our table, and what columns it's generating in the process. I've broken the different components of the SQL table onto different lines because it's easier to read this way, this same `CREATE TABLE` statement could've occurred in *one giant line* and it would behave the same way.

* We start off with the statement `CREATE TABLE games (`. this is where we are telling sequel that We are going to create a new table by the name of games and what follows after the `(` is going to be a number of creation statements that we want to occur inside that table.
* Next we have our primary key creation `id SERIAL PRIMARY KEY,`. Notice that the first word is `id`. This is where we specify the name given to the primary key (`id` is commonly used for this purpose). Next we have the word `SERIAL`. this is the part that determines that the primary key is going to increment each time a new row of data is entered into the table. Last but not least, `PRIMARY KEY,` is where we determine that this is in fact the primary key, and `,` at the end of the line indicates that another element is going to follow the element we are creating now.
* The line starting with `name` and the line starting with `publisher` follow the same pattern: the name of our column followed by `text NOT NULL`. This is where we say we're creating a new column and it's going to take in text (`TEXT`) and it cannot be empty (`NOT NULL`), Meaning the user is going to have to put something in that field when they attempt to add a new record into the table.
* On the third line the pattern is the same except instead of text we are instead putting in a date, Represented here by `DATE`
* On the final line we have the closing brace for the creation statement `)` followed by the `;` which actually runs the statement.


Ready to populate your table with some data? Check out the [next step][part-2]!


[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
[postgres-app]: http://postgresapp.com/
[part-2]: {{ site.url }}/thing.html