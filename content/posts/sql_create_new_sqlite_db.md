---
title: "SQL - Creating SQLite Databases"
date: 2023-03-10
author: "JB"
tags: ["SQLite", ".csv", ".tsv"]
categories: ["SQL"]
draft: false
---

![yuge file](/sql_bernie_yuge_file.png)

When you have a flat file (.csv, .tsv, .etc) with far too many rows for a spreadsheet editor like Excel and a file size so large (think multiple GBs) it's unwieldy in a text editor like Sublime Text, consider creating a SQLite database with it. It's fast and painless. Unlike the undisputed [GOAT](https://wgbh.brightspotcdn.com/dims4/default/a620ec1/2147483647/strip/true/crop/1920x1080+0+0/resize/1600x900!/quality/70/?url=https%3A%2F%2Fwgbh-brightspot.s3.amazonaws.com%2F99%2F20%2Fc06c226143969fb3d882e37c3389%2Ftom-brady-v2.png) of SQL databases, Postgre, SQLite doesn't require the setup of a database server. It doesn't actually require *anything*. It will live on your computer like any other file. 

Instead of:
1. starting the server
2. creating a db
3. creating a schema
4. defining a table's structure
5. reading in the file

with SQLite just :one: command will create your db almost instantly!

To create the SQLite database:

> Mac 
> - Open Terminal
> - Navigate (`cd`) to the folder you want the database to live inside
> - Type `touch database_name.db` and hit return   
> - Replace `database_name` with the name you want for your db

>:window: Windows
> - Open Command Prompt
> - Navigate (`cd`) to the folder you want the database to live inside
> - Type `database_name.db` and hit return   
> - Replace `database_name` with the name you want for your db

>:penguin: Linux
> - Open Terminal
> - Navigate (`cd`) to the folder you want the database to live inside
> - Type `sqlite3 database_name.db` and hit return   
> - Replace `database_name` with the name you want for your db

Mac Terminal example:  

![terminal gif](/sql_sqlite_terminal_touch_db.gif)

Now use Finder (Mac) or File Explorer (Windows) to navigate to the newly created database file. Double-click it to open in your default database viewer or you can right-click it and choose the viewer of your choice. 

From there, you can create a new table using TablePlus GUI Tool for SQLite.