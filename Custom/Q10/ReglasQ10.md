1. Si el tipo de dato de una colección es List, no usar .Count() para contar la cantidad de elementos de la colección. Usar .Count en su lugar.
2. Si el tipo de dato de una colección es un Array, no usar .Count() para contar la cantidad de elementos de la colección. Usar .Lenght en su lugar.
3. Para contar la cantidad de elementos de una colección, usar .Any() o .Count > 0 (para el caso del tipo de dato List). No usar .Count() > 0.
4. Si se va a usar LINQ para contar elementos o determinar que elementos cumplen una condición, no usar .Count() o .Any() directamente después de .Where(). En su lugar, se podría quitar el .Where() y ya sea el .Any() el .Count() tendrían el Func que previamente tenía el .Where retirado.
5. En Q10 se suelen manejar ViewModels, FormModels, JobModels, Modelos Light (viewmodels resumidos) y cacheModels. Evitar Usar SessionManager en los Viewmodels, light Viewmodels y JobModels. En los demás si se permitiría (FormModels).
No obstante, se tendrían excepciones como: ObtenerInfoInstitucion, ObtenerMasterInfoInstitucion, ConfigurarInfoInstitucion, ConfigurarInfoUsuario, FileHostingService, TempFileHostingService, EsMaster, etc. Las excepciones corresponden a métodos que no dependen de si hay o no sesión. Igual, sería bueno dejar la alerta para estos últimos casos.
6. 
