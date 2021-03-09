# dotnet-core-sqldb-azureapp
A simple TODO List MVC application to demonstrates how to build data-driven .NET Core apps in Azure App Service

Step 1. Push you project to git.

Step 2. Create Azure App Service and publish your code using the app service.

Step 3 -> Migrate database after updating connection string in startup.cs file. Use below command for migration
bash command:
# Delete old migrations
rm -r Migrations
# Recreate migrations
dotnet ef migrations add InitialCreate

# Set connection string to production database
# PowerShell
$env:ConnectionStrings:MyDbConnection="<connection-string>"
# CMD (no quotes)
set ConnectionStrings:MyDbConnection=<connection-string>
# Bash (no quotes)
export ConnectionStrings__MyDbConnection=<connection-string>

# Run migrations
dotnet ef database update

Step 4 -> Run with azure app service url.
