
# Laboratorio 4 - Sistema de Almacén

¡Hola profesor! ¿Cómo le va?

Este documento contiene información importante para que el programa funcione correctamente. A continuación encontrarás un script SQL para crear y utilizar la base de datos necesaria para mi Laboratorio 4 (que implementé sobre un sistema de almacén similar al visto en clase).

## Configuración de la base de datos

1. Copia y pega el siguiente script en una nueva consulta ("New Query") en SQL Server Management Studio:

```sql
IF NOT EXISTS (SELECT name FROM sys.databases WHERE name = 'Almacen')
BEGIN
    CREATE DATABASE Almacen;
    PRINT 'Base de datos Almacen creada.';
END
GO

USE Almacen;
GO

IF NOT EXISTS (SELECT * FROM sys.tables WHERE name = 'Productos')
BEGIN
    CREATE TABLE Productos (
        Id INT PRIMARY KEY IDENTITY,
        Nombre NVARCHAR(100) NOT NULL,
        Descripcion NVARCHAR(500) NOT NULL,
        Precio DECIMAL(18,2) NOT NULL,
        Cantidad INT NOT NULL
    );
    PRINT 'Tabla Productos creada.';
END
GO
```

## Configuración de la conexión

Por último, recuerda cambiar la cadena de conexión en el archivo `appsettings.json`:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(Aquí);Database=Almacen;Trusted_Connection=True;TrustServerCertificate=true;"
  }
}
```

## Notas finales

He logrado hacer funcionar todo correctamente después de resolver los problemas que tuve durante las clases. Intenté aplicar tanto lo visto en clase como conocimientos adquiridos por mi cuenta, y puedo asegurar que el programa funciona adecuadamente. Si tienes alguna duda, estaré encantado de revisarlo contigo directamente desde mi PC.
