# ASP.NET Core with PostgreSQL and Docker Demo

Application demo designed to show how ASP.NET Core and PostgreSQL can be run in Docker containers. 
The app uses Entity Framework to create a simple database that stores Docker commands and examples.

## To run the app with Docker Containers:

### Running the App with Docker Compose

1. Install `Docker for Mac` or `Docker for Windows` (or Docker Toolbox: http://docker.com/toolbox if you have to)

1. Navigate to `src/AspNetCorePostgreSQLDockerApp` in a console window

1. Install Node on your local system and run the following commands in a command window:

    `npm install`

    `npm run tsc:w`

1. Open a separate command prompt window.

3. Run `docker-compose build`

4. Run `docker-compose up`

1. Navigate to http://localhost:5000 (http://192.168.99.100:5000 if using Docker Toolbox) in your browser to view the site.


## myNote

1. Postgres data change is out side the container, using a volumn
2. start to use logger.logDebug()..

## build
docker build . -f aspnetcore.production.dockerfile -t lelehehe/dotnet:1.0.0

docker run -d --name my-postgres -e POSTGRES_PASSWORD=password postgres
docker run -d -p 5000:5000 --link my-postgres:postgres lelehehe/dotnet:1.0.0
after 10 seconds, go to 
http://localhost:5000

mymac:AspNetCorePostgreSQLDockerApp mike$ dotnet restore
after that, ctrl+shift+b would build the project succeeded
to debug in local mode, need to change connection strings in file: 
/Users/mike/Documents/GitHub/AspNetCorePostgreSQLDockerApp/src/AspNetCorePostgreSQLDockerApp/Program.cs


