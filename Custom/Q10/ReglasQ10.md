1. Si el tipo de dato de una colección es List, no usar .Count() para contar la cantidad de elementos de la colección. Usar .Count en su lugar.
2. Si el tipo de dato de una colección es un Array, no usar .Count() para contar la cantidad de elementos de la colección. Usar .Lenght en su lugar.
3. Para contar la cantidad de elementos de una colección, usar .Any() o .Count > 0 (para el caso del tipo de dato List). No usar .Count() > 0.
4. Si se va a usar LINQ para contar elementos o determinar que elementos cumplen una condición, no usar .Count() o .Any() directamente después de .Where(). En su lugar, se podría quitar el .Where() y ya sea el .Any() el .Count() tendrían el Func que previamente tenía el .Where retirado.
5. En Q10 se suelen manejar ViewModels, FormModels, JobModels, Modelos Light (viewmodels resumidos) y cacheModels. Evitar Usar SessionManager en los Viewmodels, light Viewmodels y JobModels. En los demás si se permitiría (FormModels).
No obstante, se tendrían excepciones como (donde sí se permitiría el uso de SessionManager, ya que allí, se tendrían métodos que se pueden invocar independientemente de sí hay sesión o no): ObtenerInfoInstitucion, ObtenerMasterInfoInstitucion, ConfigurarInfoInstitucion, ConfigurarInfoUsuario, FileHostingService, TempFileHostingService, EsMaster, etc. Para los demás casos, explicitamente indicar la alerta de que no es posible hacer eso, ejemplo: cuando invocan propiedades de InfoInstitucion o InfoUsuario a través del SessionManager.
6. No permitir declarar variables con 'var' en javascript o jquery. En su lugar usar let o const.
7. Siempre que se hagan peticiones rest, recomendar hacerlo por MvcApplication.GetHttpClient(), ya que en el proyecto se dispone de una estancia singleton para el client.
8. Validar errores de ortográfica, mayúsculas mal puestas o variables mal nombradas. Tener en cuenta incluso los comentarios.
9. No hacer invocaciones de métodos que internamente invoquen sp's para retornar información vía Dapper (Ej: con ExecuteQuery, ExecuteQueryAsync, etc) dentro de loops como foreach, for, while, etc. En su lugar, se debe solicitar usar o crear un sp masivo, que se invoque por fuera del loop.
10. 
