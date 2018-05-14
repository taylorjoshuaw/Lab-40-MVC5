# Movie Collection (ASP.NET 4.6.1)

## Description

Movie Collection is a simple demonstration application of ASP.NET, MVC, and Entity Framework using .NET Framework rather than .NET Core. CRUD operations have been provided to create, read, update, and delete movies from a local database. This can be accessed via the "Movies" link in the top navigation bar.

## Screenshot

![Movies Screenshot](/assets/movie.JPG)

## Controllers

### Home

The Home controller provides static content via its Index action (home landing page
for the site), About action, and Contact action.

#### Index

Returns a ViewResult for the controller's Index view, which is the home landing page
when the user does not provide any routing.

#### About

Returns a ViewResult for the controller's About view which gives a brief
explantion of the capabilities of the site.

#### Contact

Returns a ViewResult for the controller's Contact view which gives some
contact information for the author of the site.

### Movies

The Movies controller provides a means of performing CRUD operations on Movie
entities within the backing, local database. Additionally, users can filter
movies by title and genre.

#### Index

Provides a listing of all movies in the backing database. Optionally allows
users to filter these results by title and/or genre.

#### Create

Provides the user with a form with which the user can create a new Movie entity
to store in the backing database. On POST, this action will actually commit
the new movie to the database.

#### Edit

Provides the user with a form with which the user can modify an existing
Movie entity in the database. On POST, the action commits the new Movie state
to the database.

#### Delete

Provides the user with a confirmation prompt along with a summary of the Movie
entity they chose to delete. If the user confirms the deletion, this action
will delete the Movie entity from the database on POST.

#### Details

Provides the user with details about the various properties contained within
an existing Movie entity in the database.

## Models

### Movie

Contains the following properties to allow for code-first migrations using
Entity Framework:

- _int_ Id - Primary key for each Movie entity in the database
- _DateTime_ ReleaseDate - The date on which the movie was released
- _string_ Genre - The genre of the movie
- _decimal_ Price - The price of purchasing the movie on DVD
- _string_ Rating - The MPAA content rating for the movie (G, PG, PG-13, R, NC-17). Marked as "NR" if the movie has not been rated by the MPAA.

## Change Log

- 5.14.2018 - [Joshua Taylor](mailto:taylor.joshua88@gmail.com) - Initial
release. No unit testing.