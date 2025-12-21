# AspNetMvcTest - .NET 10 Application

This is an ASP.NET Core MVC application that has been migrated from .NET Framework 4.8.1 to .NET 10.

## Prerequisites

- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) (version 10.0.100 or later)

## Running the Application

### Using the command line

1. Navigate to the project directory:
   ```bash
   cd AspNetMvcTest
   ```

2. Run the application:
   ```bash
   dotnet run
   ```

3. Open your browser and navigate to:
   - HTTPS: https://localhost:7265
   - HTTP: http://localhost:5265

### Using Visual Studio

1. Open `AspNetMvcTest.sln`
2. Press F5 to run the application

## Building the Application

To build the application:
```bash
dotnet build
```

To build in Release mode:
```bash
dotnet build -c Release
```

## Publishing the Application

To publish the application for deployment:
```bash
dotnet publish -c Release -o ./publish
```

## Project Structure

```
AspNetMvcTest/
├── Controllers/          # MVC Controllers
│   └── HomeController.cs
├── Views/               # Razor Views
│   ├── Home/
│   │   ├── Index.cshtml
│   │   ├── About.cshtml
│   │   └── Contact.cshtml
│   ├── Shared/
│   │   ├── _Layout.cshtml
│   │   └── Error.cshtml
│   ├── _ViewStart.cshtml
│   └── _ViewImports.cshtml
├── wwwroot/             # Static files
│   ├── Content/         # CSS files
│   ├── Scripts/         # JavaScript files
│   └── favicon.ico
├── Properties/
│   └── launchSettings.json
├── appsettings.json
├── appsettings.Development.json
├── Program.cs           # Application entry point
└── AspNetMvcTest.csproj
```

## Migration Information

This application was migrated from .NET Framework 4.8.1 to .NET 10. For detailed migration information, see:
- [Migration Summary](../.appmod/.migration/migration-summary.md)
- [Migration Plan](../.appmod/.migration/plan.md)
- [Migration Progress](../.appmod/.migration/progress.md)

## Key Changes from .NET Framework

- **Project File**: Converted to SDK-style project
- **Startup**: Uses minimal hosting model in Program.cs (no Global.asax)
- **Configuration**: Uses appsettings.json instead of Web.config
- **Static Files**: Served from wwwroot directory
- **Views**: Use ASP.NET Core tag helpers

## Features

- Home page with application information
- About page with application description
- Contact page with contact information
- Bootstrap 5.2.3 for responsive design
- jQuery 3.6.4 for client-side interactivity

## Technologies

- .NET 10.0
- ASP.NET Core MVC
- Bootstrap 5.2.3
- jQuery 3.6.4
- Razor Views

## License

See the repository LICENSE file for details.
