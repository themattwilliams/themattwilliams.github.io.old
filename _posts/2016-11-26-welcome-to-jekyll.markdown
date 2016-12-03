---
layout: post
title:  "Using Postgres: Creating and Populating a Database — A Friendly Tutorial"
date:   2016-11-26 17:51:55 -0800
categories: sql tutorial
---

##Getting Postgres Installed and Set Up

Okay, you decided to learn SQL. More than just learning SQL, you’ve decided to learn Postgres. Good for you! Postgres is amazing and it’s pretty commonly used out there in the real world, so I want to congratulate you on making the right choice.

Let’s dive right in. There are a number of different ways to do this, but I recommend downloading and installing the [happy little elephant icon installation][postgres-app]. That will spin up your PSQL server 🐘.

Now after you’ve installed Postgres, fire up your terminal and pop into Postgres by typing ```psql``` on the command line.

When you do that you should see a Postgres version number at the top and a friendly reminder that you can type help for… You guessed it… help!

```
psql (9.6.1)
Type "help" for help.
```

You should also see a command line with your username and the ```#```. This is where you’re going to enter your SQL commands. To my case my username is labyrinth, so in my examples you are to see my username being used just like this:

```
labyrinth-#
```
##Creating a New Database and Populating it with Data

Now that we're inside our Postgres command line, we need to actually create a database. You see, the database is where we put all our tables, and our tables is where we put all our data. You can think of the Postgres database as a filing cabinet (**database**), and the filing cabinet is filled with printed out spreadsheets (**tables**).

For our example, we are going to create a new database which stores a list of the best video games of all times which I have unceremoniously selected from my personal preferences. Once we fill this new video game database with information, we will be able to manipulate it and see all the nifty ways that Postgres can play with our data to give us specific results! 

To create the database we simply use the ```CREATE DATABASE``` command as seen below. We will then see the output of the command on the next line. In this case ```CREATE DATABASE```

```
labyrinth=# CREATE DATABASE video_games;
CREATE DATABASE
```

Okay great! Now that we have our database set up, we will have to create a table *in* the database on which we will store our information (Remember you can imagine this as a file in the filing cabinet).

Let’s create a table that’s going to hold all our games. We will call it ```games_table```. I know, The title may not seem like it's particularly clever But when you're creating tables, you want the names to be as plainly descriptive as possible. ```happy_table``` is not a particularly useful name unless you're actually saving something for which happiness has a meaningful, primary and specific descriptor of the data itself.

When we create the table we have to specify what sort of information each column in the table is going to hold. For our purposes, we will use a couple of different columns (Remember, you can think of these as a column on a spreadsheet). We will have a column for the name, release date, game publisher and purchase price of each game.

| name | release_date | publisher |
|------|--------------|-----------|
|      |              |           |

When creating

But there’s something else! We’re going to need what’s called a primary key. A primary key is basically a number that’s associated with each new entry in our table. Our primary key will be an integer, it will increment with each new entry into the table. Basically just keep in mind this is a unique way to identify each record in the table. It will happen automatically once you create it initially. You don’t have to fuss with it and in truth, you really shouldn’t.







{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
\#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
[postgres-app]: http://postgresapp.com/
