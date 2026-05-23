# .NET CLI (`dotnet`)

## Project Creation & Management

| Command | Description |
| :--- | :--- |
| `dotnet new <template>` | Create a new project (e.g., `console`, `webapi`, `mvc`, `classlib`) |
| `dotnet new list` | List all available project templates |
| `dotnet new sln -n <Name>`| Create a new empty Solution file (`.sln`) |
| `dotnet sln add <project>`| Add a project (`.csproj`) to a solution |

## Build & Execution

| Command | Description |
| :--- | :--- |
| `dotnet build` | Build a project and all of its dependencies |
| `dotnet run` | Build and run the application |
| `dotnet run --project <path>` | Run a specific project in a solution |
| `dotnet watch run` | Run the project and restart/hot-reload automatically on file changes |
| `dotnet clean` | Clean the output of a project (`bin/` and `obj/` folders) |

## Packages & Dependencies (NuGet)

| Command | Description |
| :--- | :--- |
| `dotnet add package <pkg>` | Add a NuGet package reference to a project |
| `dotnet remove package <pkg>`| Remove a NuGet package reference |
| `dotnet list package` | List installed packages for a project |
| `dotnet restore` | Restore dependencies and tools of a project |

## Testing & Publishing

| Command | Description |
| :--- | :--- |
| `dotnet test` | Run unit tests using the test runner configured in the project |
| `dotnet publish -c Release` | Pack the application and its dependencies into a folder for deployment |
| `dotnet publish -c Release -r linux-x64 --self-contained` | Publish as a self-contained executable for Linux (includes the .NET runtime) |

## Entity Framework Core (EF Core)

If you have the `dotnet-ef` global tool installed (`dotnet tool install --global dotnet-ef`).

| Command | Description |
| :--- | :--- |
| `dotnet ef migrations add <Name>` | Add a new migration |
| `dotnet ef database update` | Update the database to the latest migration |
| `dotnet ef migrations remove` | Remove the last migration (if not yet applied to the DB) |

## Examples

```bash
# 1. Create a new Web API project and run it with Hot Reload
dotnet new webapi -n MyApi
cd MyApi
dotnet watch run

# 2. Add an Entity Framework Core package
dotnet add package Microsoft.EntityFrameworkCore.SqlServer

# 3. Create a solution, add two projects to it, and link them
dotnet new sln -n MyApp
dotnet new console -n MyApp.Console
dotnet new xunit -n MyApp.Tests
dotnet sln add MyApp.Console MyApp.Tests
# Add a reference from the Tests project to the Console project
dotnet add MyApp.Tests reference MyApp.Console
```
