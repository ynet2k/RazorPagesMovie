<Get Started>
dotnet new webapp -o RazorPagesMovie
code -r RazorPagesMovie

dotnet dev-certs https --trust
</Get Started>

<Add model>
dotnet tool install --global dotnet-ef
dotnet tool install --global dotnet-aspnet-codegenerator
dotnet add package Microsoft.EntityFrameworkCore.SQLite
dotnet add package Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.Extensions.Logging.Debug

dotnet-aspnet-codegenerator razorpage -m Movie -dc RazorPagesMovieContext -udl -outDir Pages\Movies --referenceScriptLibraries

dotnet tool install --global dotnet-ef

dotnet ef migrations add InitialCreate
dotnet ef database update
</Add model>

<Scaffolding>

</Scaffolding>
