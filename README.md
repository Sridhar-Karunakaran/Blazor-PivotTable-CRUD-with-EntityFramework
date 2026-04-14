# Blazor Pivot Table CRUD with Entity Framework & SQL Server

> **Build powerful data management applications with Blazor, Syncfusion Pivot Table, and Entity Framework**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![.NET Version](https://img.shields.io/badge/.NET-7.0-512BD4?logo=.net)](https://dotnet.microsoft.com)
[![Blazor](https://img.shields.io/badge/Blazor-Server-blueviolet?logo=blazor)](https://blazor.net)
[![Entity Framework](https://img.shields.io/badge/Entity%20Framework%20Core-7.0.5-green?logo=.net)](https://github.com/dotnet/efcore)
[![Syncfusion](https://img.shields.io/badge/Syncfusion-21.2.5-1F88D9)](https://www.syncfusion.com)

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Quick Start](#quick-start)
- [Project Structure](#project-structure)
- [Core Concepts](#core-concepts)
- [Usage & Examples](#usage--examples)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## 🎯 Overview

This Blazor Server application demonstrates **production-ready CRUD operations** on the [Syncfusion Blazor Pivot Table](https://www.syncfusion.com/blazor-components/blazor-pivot-table) integrated with **SQL Server** and **Entity Framework Core**. Perfect for developers building enterprise data analysis dashboards and real-time reporting solutions.

### What Problem Does This Solve?

- **Complex Data Operations**: Simplifies create, read, update, and delete operations on pivot table data
- **Database Integration**: Demonstrates seamless SQL Server integration with Blazor
- **Entity Framework Usage**: Best practices for ORM-based data access in Blazor applications
- **Real-Time Updates**: Real-time pivot table updates reflecting database changes

### Why Choose This Project?

✅ **Production-Ready Code**: Battle-tested patterns for enterprise applications  
✅ **Complete CRUD Implementation**: Full create, read, update, delete workflow  
✅ **SQL Server Integration**: Direct database connectivity with NORTHWIND sample database  
✅ **Syncfusion Components**: Professional UI components for modern dashboards  
✅ **Entity Framework Best Practices**: Proper data access layer architecture  

## ✨ Key Features

- **📊 Full CRUD Operations**: Create, Read, Update, and Delete pivot table data seamlessly
- **🗄️ SQL Server Integration**: Direct integration with SQL Server databases (NORTHWIND included)
- **🔄 Real-Time Data Sync**: Automatic synchronization between pivot table and database
- **🎨 Professional UI**: Syncfusion Pivot Table with modern styling and themes
- **⚡ Entity Framework ORM**: Type-safe database queries with LINQ
- **📱 Responsive Design**: Mobile-friendly Blazor Server interface
- **🔐 Type-Safe Operations**: C# strong typing ensures compile-time safety
- **🛠️ Data Access Layer**: Separated data access layer (OrderDataAccessLayer) for clean architecture
- **📈 Scalable Architecture**: Ready to extend with additional entities and operations

## 🛠️ Technology Stack

| Component | Version | Purpose |
|-----------|---------|---------|
| **.NET Core** | 7.0+ | Application Framework |
| **Blazor Server** | .NET 7.0 | Interactive Web UI |
| **Entity Framework Core** | 7.0.5 | ORM & Data Access |
| **SQL Server** | Latest | Relational Database |
| **Syncfusion Blazor Pivot Table** | 21.2.5 | Advanced Data Visualization |
| **Syncfusion Themes** | 21.1.41 | UI Styling |
| **System.Linq.Dynamic.Core** | 1.6.0.2 | Dynamic LINQ Queries |

### Supported Platforms

- ✅ Windows 10/11
- ✅ macOS (with .NET SDK)
- ✅ Linux (with .NET SDK)
- ✅ Modern Browsers: Chrome, Firefox, Edge, Safari

## 📋 Prerequisites

Before getting started, ensure you have the following installed:

- **[Visual Studio 2022](https://visualstudio.microsoft.com/downloads/)** (Community or Professional) with Blazor workload
  - Or **Visual Studio Code** with C# extension
- **[.NET 7.0 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/7.0)** or later
- **[SQL Server 2019](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)** or Express edition
- **Git** for version control

### Optional

- **SQL Server Management Studio** for database management
- **Postman** for API testing (if extending with API endpoints)

## 🚀 Quick Start

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/Blazor-PivotTable-CRUD-with-EntityFramework.git
cd Blazor-PivotTable-CRUD-with-EntityFramework
```

### 2️⃣ Open the Solution

```bash
cd MyBlazorApp
# Open with Visual Studio 2022
start MyBlazorApp.sln

# Or use Visual Studio Code
code .
```

### 3️⃣ Restore NuGet Packages

```bash
dotnet restore
```

### 4️⃣ Update Database Connection

Edit `appsettings.json` and configure your SQL Server connection:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=YOUR_SERVER;Database=NORTHWND;Trusted_Connection=true;"
  }
}
```

### 5️⃣ Run Migrations (if needed)

```bash
dotnet ef database update
```

### 6️⃣ Build & Run

```bash
dotnet build
dotnet run
```

Navigate to `https://localhost:7001` (or your configured port) in your browser.

## 📁 Project Structure

```
Blazor-PivotTable-CRUD-with-EntityFramework/
│
├── MyBlazorApp/                    # Main application folder
│   ├── MyBlazorApp.csproj         # Project file with dependencies
│   ├── Program.cs                 # Application startup configuration
│   ├── App.razor                  # Root component
│   │
│   ├── Controllers/
│   │   └── PivotController.cs     # API endpoints for pivot table data
│   │
│   ├── Data/                      # Data access layer
│   │   ├── OrderContext.cs        # Entity Framework DbContext
│   │   ├── Orders.cs              # Order entity model
│   │   ├── OrderDataAccessLayer.cs # Data access operations
│   │   ├── WeatherForecast.cs     # Sample entity
│   │   └── WeatherForecastService.cs
│   │
│   ├── Pages/
│   │   ├── Index.razor            # Main pivot table component
│   │   ├── HttpClient.razor       # HTTP client configuration
│   │   └── Error.cshtml           # Error handling page
│   │
│   ├── Shared/
│   │   ├── MainLayout.razor       # Main layout component
│   │   ├── NavMenu.razor          # Navigation menu
│   │   └── SurveyPrompt.razor     # Survey component
│   │
│   ├── wwwroot/                   # Static assets
│   │   ├── css/                   # Stylesheets
│   │   ├── js/                    # JavaScript files
│   │   └── images/                # Image assets
│   │
│   ├── App_Data/
│   │   └── NORTHWND.MDF           # SQL Server sample database
│   │
│   ├── appsettings.json           # Configuration settings
│   └── appsettings.Development.json
│
└── README.md                       # This file
```

### Key Files Explained

| File | Purpose |
|------|---------|
| `PivotController.cs` | REST API endpoints for CRUD operations on pivot data |
| `OrderContext.cs` | Entity Framework DbContext defining database schema |
| `Orders.cs` | Entity model representing order records |
| `OrderDataAccessLayer.cs` | Business logic layer for data operations |
| `Index.razor` | Main Blazor component displaying the pivot table |

## 🧠 Core Concepts

### Entity Framework Architecture

The application uses a **layered architecture** pattern:

```
Blazor UI (Index.razor)
        ↓
PivotController (API Layer)
        ↓
OrderDataAccessLayer (Business Logic)
        ↓
OrderContext (Entity Framework DbContext)
        ↓
SQL Server Database
```

### Database Context

`OrderContext` inherits from `DbContext` and manages:
- Entity mappings
- Database connections
- Transaction management
- Change tracking

### Data Access Layer

`OrderDataAccessLayer` provides:
- CRUD method abstractions
- Query filtering and sorting
- Error handling
- Transaction support

## 💡 Usage & Examples

### Viewing Pivot Table Data

The Index.razor component loads data via the PivotController:

```csharp
// PivotController.cs - Get all orders for pivot analysis
[HttpGet("api/orders")]
public IActionResult GetOrders()
{
    var orders = _dataAccessLayer.GetAllOrders();
    return Ok(orders);
}
```

### Adding New Orders (Create)

```csharp
// OrderDataAccessLayer.cs
public void AddOrder(Orders order)
{
    using (OrderContext context = new OrderContext())
    {
        context.Orders.Add(order);
        context.SaveChanges();
    }
}
```

### Updating Existing Data

```csharp
public void UpdateOrder(Orders order)
{
    using (OrderContext context = new OrderContext())
    {
        context.Entry(order).State = EntityState.Modified;
        context.SaveChanges();
    }
}
```

### Deleting Records

```csharp
public void DeleteOrder(int orderId)
{
    using (OrderContext context = new OrderContext())
    {
        var order = context.Orders.Find(orderId);
        if (order != null)
        {
            context.Orders.Remove(order);
            context.SaveChanges();
        }
    }
}
```

## ⚙️ Configuration

### Database Connection String

Configure in `appsettings.json`:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=NORTHWND;Trusted_Connection=true;"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information"
    }
  }
}
```

### Syncfusion License

For production use, register your Syncfusion license in `Program.cs`:

```csharp
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR_LICENSE_KEY");
```

### Entity Framework Options

Customize DbContext in `OrderContext.cs`:

```csharp
protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
{
    optionsBuilder.UseSqlServer("your_connection_string");
}
```

## 🔧 Troubleshooting

### Connection String Issues

**Problem**: "Cannot connect to database"  
**Solution**: Verify SQL Server is running and connection string is correct in `appsettings.json`

### Missing Database

**Problem**: "Database does not exist"  
**Solution**: Run `dotnet ef database create` to initialize the database

### Port Already in Use

**Problem**: "Port 7001 already in use"  
**Solution**: Change port in `launchSettings.json` or stop conflicting process

### Syncfusion Component Not Rendering

**Problem**: Pivot Table appears blank  
**Solution**: Ensure Syncfusion license is valid and all required themes are loaded

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Code Style Guidelines

- Follow [C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
- Use meaningful variable names
- Add XML documentation comments for public methods
- Include unit tests for new features

## 📄 License

This project is licensed under the **MIT License** - see the LICENSE file for details.

This means you can use, modify, and distribute this code freely, including for commercial projects, with proper attribution.

## 📞 Support

### Getting Help

- 📖 **Documentation**: Check the [Syncfusion Blazor Documentation](https://www.syncfusion.com/blazor-components)
- 🐛 **Report Issues**: [GitHub Issues](https://github.com/yourusername/Blazor-PivotTable-CRUD-with-EntityFramework/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/yourusername/Blazor-PivotTable-CRUD-with-EntityFramework/discussions)
- 📧 **Email Support**: Contact your organization's support team

### Related Resources

- [Microsoft Blazor Documentation](https://learn.microsoft.com/en-us/aspnet/core/blazor/)
- [Entity Framework Core Documentation](https://learn.microsoft.com/en-us/ef/core/)
- [Syncfusion Pivot Table Demo](https://www.syncfusion.com/blazor-components/blazor-pivot-table)
- [SQL Server Documentation](https://learn.microsoft.com/en-us/sql/sql-server/)

---

**Last Updated**: April 2026  
**Maintainers**: [Your Name/Organization]  
**Built with ❤️ for the Blazor Community**