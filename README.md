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