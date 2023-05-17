# Proyecto de Sistema de Ventas

## Descarga de base de datos

```
https://github.com/AdrianMValencia/POSDB
```

### Añadir proyectos a la solucion

```C#
dotnet sln [SolutionName] add [PathProject]
dotnet sln POS.sln add src/POS.Domain/POS.Domain.csproj
```

### Añadir Entity Framework Core

```C#
dotnet add [ProjectName] package [NamePackage]
dotnet add src/POS.Domain/POS.Domain.csproj package Microsoft.EntityFrameworkCore.SqlServer
```

### Añadir Entity Framework Core Tools or Design

```C#
dotnet add [ProjectName] package [NamePackage]
dotnet add src/POS.Domain/POS.Domain.csproj package Microsoft.EntityFrameworkCore.Tools
dotnet add src/POS.Domain/POS.Domain.csproj package Microsoft.EntityFrameworkCore.Design
dotnet add src/POS.Api/POS.Api.csproj package Microsoft.EntityFrameworkCore.Design
```

### Añadir System.Linq.Dynamic.Core

```C#
dotnet add src/POS.Infrastructure/POS.Infrastructure.csproj package System.Linq.Dynamic.Core
```

### Añadir AutoMapper

```C#
dotnet add src/POS.Application/POS.Application.csproj package AutoMapper
```

### Añadir AutoMapper.Extensions.Microsoft.DependencyInjection

```C#
dotnet add src/POS.Application/POS.Application.csproj package AutoMapper.Extensions.Microsoft.DependencyInjection
```

### Añadir Azure.Storage.Blobs

```C#
dotnet add src/POS.Application/POS.Application.csproj package Azure.Storage.Blobs
```

### Añadir FluentValidation.AspNetCore

```C#
dotnet add src/POS.Application/POS.Application.csproj package FluentValidation.AspNetCore
```

### Añadir Referencias a los Proyectos

```C#
dotnet add src/POS.Infrastructure/POS.Infrastructure.csproj reference src/POS.Domain/POS.Domain.csproj
dotnet add src/POS.Infrastructure/POS.Infrastructure.csproj reference src/POS.Utilities/POS.Utilities.csproj

dotnet add src/POS.Application/POS.Application.csproj reference src/POS.Domain/POS.Domain.csproj
dotnet add src/POS.Application/POS.Application.csproj reference src/POS.Infrastructure/POS.Infrastructure.csproj
dotnet add src/POS.Application/POS.Application.csproj reference src/POS.Utilities/POS.Utilities.csproj

dotnet add src/POS.API/POS.API.csproj reference src/POS.Application/POS.Application.csproj
dotnet add src/POS.API/POS.API.csproj reference src/POS.Infrastructure/POS.Infrastructure.csproj
dotnet add src/POS.API/POS.API.csproj reference src/POS.Utilities/POS.Utilities.csproj

dotnet add test/POS.Test/POS.Test.csproj reference src/POS.API/POS.API.csproj
```

### Realizar scaffold de la Base de Datos

```C#
dotnet ef dbcontext scaffold "Server=NameServer;Database=NameDB;User Id=User;Password=Password;TrustServerCertificate=true" Microsoft.EntityFrameworkCore.SqlServer -o Entities
```