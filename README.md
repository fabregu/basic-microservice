# 🧩 Microservicio Básico DB First

Microservicio desarrollado en **.NET 9** con Docker.

## 🚀 Características

- Arquitectura basada en microservicios
- RESTful API
- Soporte para Swagger
- Autenticación JWT (si aplica)
- Integración con SqlServer

## 📦 Tecnologías

- ASP.NET Core 9(WebApi)
- C#
- Entity Framework Core
- Swagger
- SQL Server
- Docker

## ⚙️ Configuración

1. Clona el repositorio:
   ```bash
   git clone https://github.com/fabregu/basic-microservice.git
   ```

2. Configura la cadena de conexión en `Program.cs`:
   ```csharp
   builder.Services.AddDbContext<ProductContext>(options =>
       options.UseSqlServer(builder.Configuration.GetConnectionString("DeffaultConnection")));
   ```

3. En `docker-compose.yaml`, asegúrate de definir correctamente las variables de entorno:
   ```yaml
   environment:
     - ASPNETCORE_ENVIRONMENT=Development
     - ConnectionStrings__DeffaultConnection=Server=host.docker.internal;Database=ProductDb;User Id=sa;Password=TUCLAVE;Encrypt=False;

4. Restaura dependencias:
   ```bash
   dotnet restore
   ```

5. Ejecuta las migraciones (si aplica):
   ```bash
   dotnet ef database update
   ```

6. Ejecuta el microservicio:
   ```bash
   dotnet run
   ```

7. Accede a Swagger UI (si está habilitado):
   ```
   http://localhost:5000/swagger
   o esta url:
   http://localhost:8001/api/product
   ```

## 📁 Estructura del Proyecto

```plaintext
├── Controllers/
├── Models/
├── Migrations/
└── Program.cs
```

## 🧪 Pruebas

```bash
dotnet test
```

## 🐳 Docker 

```bash
docker-compose build
docker-compose up
```

## Guía
https://www.youtube.com/watch?v=3ftI26leOzA

## 📄 Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más información.
