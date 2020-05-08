# snowshop
An online shop made with a dotnet core API and Angular

## command to run API server from terminal
`dotnet watch run -p API` watch for any site change and restart server every time

## command line scripts to generate the API
`dotnet -h` `dotnet new -h` help menu
`dotnet new sln` create a solution named with the current directory, or pass -n to enter a name
`dotnet new webapi -o API` create a web API template. -o specifies the output directory
`dotnet sln add API` add project to the solution
`dotnet sln list` lists projects to verify API has been added to solution
`dotnet new gitignore --force` creates a gitignore file. Pass --force if you had already a gitignore file
In VSCode with C# Extensions by jchannon: Shift Cmd P > .NET generate assets for Build and Debug

### Install Entity Framework:
Cmd Shift P > Nuget Package Manager: Add Package > Microsoft.EntityFrameworkCore
Be sure to use the exact version that you have for `Host (useful for support)` when you run `dotnet --info`
Repeat for Microsoft.EntityFrameworkCore.Sqlite
Press on restore promt or run `dotnet restore`

In API/Data/StoreContext.cs hover on the class name `StoreContext` press Cmd . and select `generate a constructor with options` and remove attributes
In Startup.cs hover over Configuration, Cmd . > initialize field from parameter

install entity framework tools globally
`dotnet tool install --global dotnet-ef --version 3.1.201`
`dotnet ef -h` 
Add Nuget Package `Microsoft.EntityFrameworkCore.Design` to use tools
`dotnet ef migrations add InitialCreate -o Data/Migrations` Create first migration

`dotnet ef database -h` shows 2 available commands: `drop` and `update`
`dotnet ef database update` to create a database and install latest migration if not specified

Shift Cmd P > Sqlite Open Database
See database in Sqlite Explorer (right click > show table)
In Sqlite Explorer, right click on `Products` > `new query [insert]`
```
-- SQLite
INSERT INTO `Products` (Id, Name)
VALUES (1, 'Product one'), (2, 'Product two'), (3, 'Product three');
```
right click > run query