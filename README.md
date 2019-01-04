# SQL-CRUD-PHC

This lab will be similar to the app we built in the [SQL-CRUD-DINOS lab](https://github.com/WDI-SEA/SQL-CRUD-DINOS).

## Set up Node/Express/Postgress project

* Create a new `seedy-phc` Node/Postgres project.
* Create a seeder file and seed the following demo-phcs into your database:

```js
[
  {
    type:"giant beaver",
    img_url:"http://www.beringia.com/sites/default/files/Giant-Beaver-banner.jpg"
  },
  {
    type:"mastodon",
    img_url:"https://cdn-images-1.medium.com/max/1200/1*a2VvYsKGApR-E1SnT5O7yQ.jpeg"
  },
  {
    type:"saber-toothed salmon",
    img_url:"https://cottagelife.com/wp-content/uploads/2014/11/Oncorhynchus_rastrosus.jpg"
  },
  {
    type:"megalonyx",
    img_url:"https://animalgeography.files.wordpress.com/2018/08/sloth-banner-e1535192925361.jpg?w=584&h=325"
  }
]
```
Refer to the [seeding notes](https://gawdiseattle.gitbooks.io/wdi/content/05-node-express/express-sequelize/seeding.html), but note that your table wont look exactly the same as your Dinosaurs table did!

* Add `express`, `ejs`, and `express-ejs-layouts` to set up your views
* Use `method-override` to make the `PUT` and `DELETE` routes work properly
* Don't forget the `body-parser` middleware to make the form data come through properly
* Since there aren't too many routes, you may opt to put them all in your main server file (as opposed to a controller)

---

## Views

### Home: 
* landing page that has a link to the _index_ view

### Index: 
* Pulls all prehistoric creatures from the database and displays them in a list.
* Each list item should link to the _show_ view for that specific PHC
* * Somewhere on this page, include a form for creating a new PHC.

### Show:
* Displays type and photo for a specific PHC.
* includes an "edit" button that takes the user to the _edit_ view
* includes a "delete" button that deletes the phc from the database and redirects back to the list of dinosaurs

### Edit:
* Form should prepopulate the existing data about the PHC that the user wants to edit.
* Submit button updates this PHC in the database and redirects back to the _index_ view.

---

## Routes

Your app should include the following routes

| VERB | URL | Action (CRUD) | Description |
|------|-----|---------------|-------------|
| GET | / | Read | landing page |
| GET | /phc | Read | lists all phcs |
| POST | /phc | Create | post new phc to database and redirect back to _index_ view |
| GET | /phc/:id | Read | shows the type and photo for a specific PHC |
| GET | /phc/edit/:id | Read | form for editting a specific PHC |
| PUT | /phc/:id | Update | updates the data for a specific PHC |
| DELETE | /phc/:id | Delete | deletes a specific PHC |

Your routes will include the `sequelize` code that peforms the CRUD operations on your database of prehistoric creatures. Refer to [these notes](https://gawdiseattle.gitbooks.io/wdi/05-node-express/express-sequelize/04usingmodels.html) and/or the [sequelize docs](http://docs.sequelizejs.com/manual/tutorial/models-usage.html) for help.
