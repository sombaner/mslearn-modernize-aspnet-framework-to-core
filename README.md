# ASP.NET MVC Migration Sample

This repository demonstrates the migration of an ASP.NET MVC 5 application from .NET Framework 4.8.1 to .NET 10.

## Migration Overview

This project has been successfully migrated from ASP.NET MVC 5 (.NET Framework 4.8.1) to ASP.NET Core MVC (.NET 10). The migration includes:

- ✅ SDK-style project format
- ✅ .NET 10 target framework
- ✅ Modern configuration system (appsettings.json)
- ✅ ASP.NET Core MVC with Razor views
- ✅ Static file serving from wwwroot
- ✅ Enhanced security headers

## Prerequisites

- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) or later

## Running the Application

1. Clone the repository
2. Navigate to the AspNetMvcTest directory
3. Run the application:

```bash
cd AspNetMvcTest
dotnet run
```

The application will be available at `http://localhost:5000` (or the port shown in the console).

## Project Structure

```
AspNetMvcTest/
├── Controllers/         # MVC Controllers
├── Views/              # Razor Views
├── wwwroot/            # Static files (CSS, JS, images)
├── Program.cs          # Application entry point
├── appsettings.json    # Application configuration
└── AspNetMvcTest.csproj # Project file
```

## Migration Details

### Key Changes

1. **Project File**: Converted from old-style .csproj to SDK-style project format
2. **Configuration**: Migrated from Web.config to appsettings.json
3. **Hosting Model**: Migrated from Global.asax to Program.cs
4. **Controllers**: Updated to use Microsoft.AspNetCore.Mvc
5. **Views**: Updated to use ASP.NET Core tag helpers
6. **Static Files**: Moved to wwwroot directory
7. **Security**: Added security headers (X-Content-Type-Options, X-Frame-Options, X-XSS-Protection)

### Security Enhancements

The migrated application includes the following security improvements:
- HSTS (HTTP Strict Transport Security) in production
- HTTPS redirection
- Security headers to prevent XSS, clickjacking, and MIME-type sniffing attacks

## Testing

Build the project:
```bash
dotnet build
```

Run the application:
```bash
dotnet run
```

## Legacy Files

The following files from the original .NET Framework project are excluded from compilation but retained for reference:
- App_Start/ (routing and bundle configuration)
- Global.asax and Global.asax.cs
- Web.config and transform files
- packages.config

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
