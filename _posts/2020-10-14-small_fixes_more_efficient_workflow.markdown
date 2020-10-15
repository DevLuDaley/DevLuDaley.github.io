---
layout: post
title:      "small fixes = a more efficient workflow"
date:       2020-10-14 23:57:51 -0400
permalink:  small_fixes_more_efficient_workflow
---

Before starting my final project I promised myself that I would invest time in imporiving my workflow. Here are two customizations that helped my workflow efficiency. My project was built on an api-only rails backend with a postgresql database and react, redux, thunk frontend. 

# the backend
I like using a seed file and maybe a tool like Faker gem to create dummy data for my database. But while building or troubleshooting a project I almost always add objects to the db and eventually the UI by submitting forms and confirming params. After a while my page would be crowded with data that I created to confirm each functionality. I knew there was a better way. After reading Rails docs and few articles I found a solution. Now I delete, recreate (from the schema files instead of the migration files), reseed the database and finally start the server. The chaining of the last command allows rails to auto start the server as soon as my new database is reseeded and ready. See the commands below.

```
source: https://guides.rubyonrails.org/active_record_migrations.html#resetting-the-database

Active Record Migrations
Migrations are a feature of Active Record that allows you to evolve your database schema over time. Rather than write schema modifications in pure SQL, migrations allow you to use a Ruby DSL to describe changes to your tables.
```


```yml
source: https://guides.rubyonrails.org/active_record_migrations.html#resetting-the-database

4.2 Setup the Database
The bin/rails db:setup command will create the database, load the schema, and initialize it with the seed data.

4.3 Resetting the Database
The bin/rails db:reset command will drop the database and set it up again. This is functionally equivalent to bin/rails db:drop db:setup.
```

Here's the chained command.
```bash
rails db:reset && rails s
```

# npm/package.json
Once i have my backend up and running I need to run `npm start` for my frontend. The issue is that my frontend also defaults to localhost:3000 which is already in use by my backend. I kept forgetting about this minor issue and wondering why my page wouldn't load. Luckily react would remind me that the port was unavailable then allow me to use a different port. But I decided that I can do better than that. So decided to change my react project's default port. After some research I updated my package.json file's `"Scripts": "Start"` value to use port 3001. 
See below. 

#### before
```js
//package.json
  "scripts": {
    "start": "react-scripts start",
		}
```
#### after
```js
//package.json
  "scripts": {
    "start": "PORT=3001 react-scripts start",
		}
```

