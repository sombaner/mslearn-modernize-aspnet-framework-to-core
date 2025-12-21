# Migration Plan: .NET Framework 4.8.1 to .NET 10

## Project Information
- **Project Name**: AspNetMvcTest
- **Source Framework**: .NET Framework 4.8.1
- **Target Framework**: .NET 10.0
- **Application Type**: ASP.NET MVC 5 → ASP.NET Core MVC

## Migration Phases

### Phase 1: Analysis ✅
- [x] Analyze current project structure
- [x] Identify dependencies and packages
- [x] Review application architecture
- [x] Document current functionality

### Phase 2: Project Conversion ✅
- [x] Convert .csproj to SDK-style project
- [x] Update target framework to net10.0
- [x] Remove packages.config
- [x] Add required NuGet packages

### Phase 3: Application Startup ✅
- [x] Create Program.cs with minimal hosting model
- [x] Remove Global.asax
- [x] Remove App_Start folder
- [x] Configure routing in Program.cs
- [x] Configure middleware pipeline

### Phase 4: Configuration ✅
- [x] Create appsettings.json
- [x] Create appsettings.Development.json
- [x] Remove Web.config files
- [x] Add launchSettings.json

### Phase 5: Code Migration ✅
- [x] Update controller namespaces
- [x] Update controller return types
- [x] Update view configuration
- [x] Create _ViewImports.cshtml
- [x] Update _Layout.cshtml with tag helpers
- [x] Move static files to wwwroot

### Phase 6: Verification ✅
- [x] Build the application
- [x] Test all pages
- [x] Code review
- [x] Document migration

## Dependencies Mapping

### Removed (.NET Framework)
- System.Web.Mvc
- System.Web.Optimization
- System.Web.Routing
- Microsoft.AspNet.Mvc
- Microsoft.AspNet.Web.Optimization
- WebGrease
- Antlr

### Added (.NET 10)
- Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation (v10.0.0)
- Built-in ASP.NET Core packages

## Key Migration Patterns

### Routing
**Before**: RouteConfig.cs in App_Start
```csharp
routes.MapRoute(
    name: "Default",
    url: "{controller}/{action}/{id}",
    defaults: new { controller = "Home", action = "Index", id = UrlParameter.Optional }
);
```

**After**: Program.cs
```csharp
app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");
```

### Controllers
**Before**: System.Web.Mvc.ActionResult
**After**: Microsoft.AspNetCore.Mvc.IActionResult

### Views
**Before**: @Html.ActionLink()
**After**: <a asp-controller="..." asp-action="...">

### Static Files
**Before**: Root directory (Content/, Scripts/)
**After**: wwwroot/ directory

## Risk Assessment
- **Low Risk**: Simple MVC application with no complex dependencies
- **No Database**: Application is UI-only, no data access layer to migrate
- **No Authentication**: No identity/auth system to migrate
- **Static Content**: All static files move cleanly to wwwroot

## Success Criteria
- [x] Application builds without errors
- [x] All pages render correctly
- [x] Navigation works
- [x] Static resources load
- [x] No breaking changes to functionality
