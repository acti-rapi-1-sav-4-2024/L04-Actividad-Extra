# Actividad Extraclase: Creando Middlewares Personalizados en ASP.NET Core

## Objetivo

* Fortalecer la comprensión de los middlewares en ASP.NET Core.
* Implementar middlewares personalizados para resolver problemas comunes en el desarrollo de APIs.
* Aprender a configurar el pipeline de middleware de una aplicación.

## Instrucciones

1. **Crea una nueva solución en ASP.NET Core:** Utiliza tu IDE favorito (Visual Studio Code, Rider, etc.) para crear una nueva aplicación web ASP.NET Core.
2. **Implementa un middleware de logging:**
   * Crea una nueva clase de middleware. Similar a `CustomExceptionHandlerMiddleware.cs` vista en clase.
   * En el método `InvokeAsync`, registra un mensaje en un log antes y después de procesar la solicitud. Puedes utilizar una biblioteca de logging como Serilog o simplemente escribir en la consola.
3. **Implementa un middleware de modo mantenimiento:**
   * Crea otro middleware que verifique un flag de mantenimiento configurada en algún lugar (por ejemplo, en `appsettings.json`) o en una variable.
   * Si el modo de mantenimiento está activado, devuelve una respuesta HTTP 503 (Servicio no disponible).
4. **Implementa un middleware para manejar excepciones:**
   * Crea un middleware que capture las excepciones que no son manejadas por otros middlewares o controladores.
   * Registra la excepción y devuelve una respuesta HTTP con un código de estado apropiado (por ejemplo, 500 - Error interno del servidor).
5. **Agrega los middlewares al pipeline de la aplicación:**
   * Todos los middlewares deben utilizar métodos de extensión.
   * Ejemplo de métodos de extensión:
      ```C#
      public static class CustomMiddlewareExtension
      {
          public static IApplicationBuilder UseCustomMiddleware(this IApplicationBuilder builder)
          {
              return builder.UseMiddleware<CustomMiddleware>();   
  
          }
      }
      ```
    Ver ejemplo en 👉 [Middleware class](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/middleware/write?view=aspnetcore-8.0#middleware-class).

## Entrega

* Subir todos los cambios al repositorio clonado.

**🎉🎉🎉 ¡Diviértete experimentando con los middlewares en ASP.NET Core! 🎉🎉🎉**

