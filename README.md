# Blazor Pivot Table CRUD with Entity Framework & SQL Server

Production-ready Blazor Server app for CRUD operations on Syncfusion Pivot Tables with SQL Server and Entity Framework Core.

## Features

- Full CRUD operations on pivot table data
- SQL Server with NORTHWIND database
- Real-time database synchronization
- Type-safe Entity Framework queries
- Syncfusion UI components
- Layered architecture design

## Tech Stack

.NET 7.0 | Blazor Server | EF Core 7.0.5 | SQL Server | Syncfusion 21.2.5

## Prerequisites

- Visual Studio 2022 or VS Code
- .NET 7.0 SDK
- SQL Server 2019+

## Quick Start

1. **Checkout** this project to a location on your disk
2. **Open** the solution file using Visual Studio 2022
3. **Restore NuGet packages** by rebuilding the solution
4. **Run** the project

Then open `https://localhost:7001` in your browser.

## Configuration

Update `appsettings.json`:
```json
{"ConnectionStrings":{"DefaultConnection":"Server=YOUR_SERVER;Database=NORTHWND;Trusted_Connection=true;"}}
```

## Architecture

**Blazor UI** → **PivotController** → **OrderDataAccessLayer** → **OrderContext** → **SQL Server**

Data flows through OrderDataAccessLayer with CRUD abstractions. OrderContext manages Entity Framework mappings.

## Key Files

- **PivotController**: API endpoints
- **OrderContext**: DbContext
- **OrderDataAccessLayer**: Business logic
- **Index.razor**: Pivot table UI