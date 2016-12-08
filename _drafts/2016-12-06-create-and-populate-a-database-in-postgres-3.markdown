---
layout: post
title:  "Using Postgres: Creating and Populating a Database — A Friendly Tutorial -- Level 3"
categories: sql tutorial
---

## Populating our New Table with Data

Okay, let's wrap this thing up. First give yourself a pat on the back, you created a new database and you created a new table inside the database!

Now we need to insert some rows of data into our new table. Before we do it let's do one more thing, let's take a look at all the data that's currently in our table. Now I know what you're thinking, you're thinking that's silly because there's nothing in the table, and you're right. Let's just take a look at how the heading of the database table is structured so we can get an idea of how the information will be laid out once we put in there.

In order to select all the columns from our database, we type the following statement into our terminal: `SELECT * FROM games;`

This statement above is called a SQL query, and can be broken down as **grab** (`SELECT`) **all columns** (`*`) in our table. The `*` is something that you'll see a lot of when playing with SQL. Just remember it means *everything*.


Here is the line that prints to your console after you type in the SQL query:

```
video_games=#
SELECT * FROM games;
 id | name | release_date | publisher
----+------+--------------+-----------
(0 rows)
```

Now it's time to insert data into our table. We will do this by adding rows of data which corresponds to each column in the table. In other words if we add a video game, we are going to add it with a name, release date and a publisher. Each video game will be a new row of data in our table.

The game StarCraft was published by Blizzard Entertainment in 1998. It also happens to be a huge hit, and it's going to be the first entry into our new database table. In order to insert into our games table we are going to do exactly what you would expect we are going to, `INSERT INTO games`. 

Now when we say we want to insert something into the games table we have to specify what parts of the games table we're actually talking about. In order to do this we're going to specify the fields into which we want to put our new information: the name of the Game is StarCraft, the release date is 3 March 1998, and the publisher is Blizzard (I know the date looks a little weird, but more on that later). 

So first we specify where we are going to put our data, and we use braces to specify what we're referring to. `INSERT INTO games (name, release_date, publisher)` tells the computer that we're going to insert our new information into the games table in these three specific fields and in this specific order.

Next we have to specify what values we want to put inside those fields. Because we're talking about specifying *values* we use our next keyword, `VALUES`. `VALUES` is the word we put right before we tell the computer what values we're actually talking about. In essence we're saying hey, the values that I want to give you are coming up next, get ready!

Remember, the name of the Game is StarCraft, the release date is 3 March 1998, and the publisher is Blizzard. That is the information we are going to pass as our values. So given that we want to `INSERT INTO` our games table the `VALUES` about StarCraft, our SQL statement is the following:

```
video_games=#                                                                                      
INSERT INTO games (name, release_date, publisher)  VALUES (
'Starcraft', '1998/03/21', 'Blizzard'
);
INSERT 0 1
```

Order matters. Notice that the data that we're inserting matches up with the columns we specified previously. If we were to switch up the words StarCraft and the word Blizzard and say `'Blizzard', '1998/03/21', 'Starcraft'`, we would have the *name* of Blizzard and the *publisher* of StarCraft, And that's just silly. 

The line at the bottom says `INSERT 0 1`. For our purposes just remember that the second number refers to the number of *rows* of data that we have inserted into our table. In this case we only inserted one game (Starcraft) and so the insertion number is`1`.

...and congratulations! You've successfully inserted a row into a table inside a database, all of which you created yourself!

A couple of things to keep in mind as you move forward on your SQL database journey: 

* When you're inserting dates, it's good to use the computer's date format which is **year month day**. The benefit of using this type of date format is that you can sort your dates and they will always come out in the correct chronological order. If you mix up this format sometimes you'll run into sticky situations.
* When you're entering your `VALUES` into your table, make sure to wrap them in single quotes `'` and not double quotes `"`. Data being inserted into the `VALUES` field needs single quotes.


Want to review creating a table in your database? Check out the [previous step][part-2]!


[postgres-app]: http://postgresapp.com/
[part-2]: {{ site.baseurl }}{% post_url 2016-12-04-create-and-populate-a-database-in-postgres-2 %}