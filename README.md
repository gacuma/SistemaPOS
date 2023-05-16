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

### Realizar migraciones

```C#
dotnet ef migrations add [NameMigration]
```

### Actualizar Base de Datos

```C#
dotnet ef database update
```

### Remover una migracion

```C#
dotnet ef migrations remove
```

### Habilitar certificado SSL

```C#
dotnet dev-certs https --trust
```

### Para poder ejecutar la aplicacion con https

Para las aplicaciones creadas con .Net 7 se realizaron cambios en la configuracion para https. Se generan dos perfiles uno por default que es el de http y otro el https, por lo que tendra que hacer referencia al perfil con el cual desea ejecutar su aplicación o modificar el launchSettings de su proyecto.

```C#
dotnet run --launch-profile https
```