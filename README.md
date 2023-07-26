# supabaseWebAPI
This is an MVC pattern API using the C# Supabase Client. The project was built as a proof of concept for a mob-programming project and allows for operations on two Supabase Table, with the addition of the requisite Supabase Url and API key as env variables where noted. These are stored as dotnet user-secrets.

The MVC pattern was used as practice to set up this style of controllers, as well as adding new controllers to the same project.

Testing of the controllers was set up using Xunit to automate checking of response types.

The Supabase Docker image was used to create a testable docker database, rather than connecting to the actual project.

## The Models - Jobs

The table in question contained a model for the table items as:
- IF - GUID (primary key within the table)
- Name - String
- Email - String
- CreatedAt - DateTime

The progam also includes contracts for the DTOs based on requests and responses relating to the above model.

## The Routes - Jobs

All routes are based on the /jobdescriptions endpoints.  The following operations are contained within the API:

- GET - /jobdescriptions/ - returns a list of all job descriptions.
- GET - /jobdescriptions/{id} - returns the job description identified.
- POST - /jobdescriptions - adds a job description based on teh request and returns the job description id generated by the table.
- PUT - /jobdescriptions/{id} - updates the job description identified.
- DELETE - /jobdescriptions/{id} - deletes the selected job description.

## The Models

The table in question contained a model for the table items as:
- Id - GUID (primary key within the table)
- Name - String
- Email - String
- CreatedAt - DateTime

The progam also includes contracts for the DTOs based on requests and responses relating to the above model.

## The Routes

All routes are based on the /jobdescriptions endpoints.  The following operations are contained within the API:

- GET - /developers/ - returns a list of all developers.
- GET - /developers/{id} - returns the developer identified.
- POST - /developers - adds a developers based on the request and returns the developer's id generated by the table.
- PUT - /developers/{id} - updates the developer identified.
- DELETE - /developers/{id} - deletes the selected developer.

## Next Steps

As the project developed, it became clear that the use of the Supabase client was not worth the loss of Entity Framework. We have therefore migrated the project to a postgres C# backend, connecting to the supabase database via a connection string.
