---
layout: post
title:  "Using Postgres: Creating and Populating a Database — A Friendly Tutorial -- Level 1"
date:   2016-12-04 17:51:55 -0800
categories: sql tutorial
---


<img src="http://blog.nordeus.com/files/libraryblog/articles/postgres/postgresql_logo.png" alt="PostgreSQL" style="height: 200px;"/>

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

Okay, now is where the real fun begins! it's time to [create a table inside our database][part-2]!


[postgres-app]: http://postgresapp.com/
[part-2]: {{ site.baseurl }}{% post_url 2016-12-04-create-and-populate-a-database-in-postgres-2 %}