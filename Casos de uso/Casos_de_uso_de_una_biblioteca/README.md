<img src="Biblioteca.png">

|  Actor | Usuario |
|---|---|
| Descripción  | El usuario utiliza el sistema de la biblioteca para buscar,prestar y devolver libros  |
| Características  | Pueden buscar diferentes libros basado en parametros como genero. |
| Relaciones | Tiene dos relaciones con el actor bibliotecario y son Buscar libro y prestar libro.  |
| Referencias | Buscar libro,Prestar Libro,Devolver libro |   
| Autor  | Joseph Vanegas Caicedo |
|Fecha | 31/01/2024 |

|  Actor | Bibliotecario |
|---|---|
| Descripción  | Manejar el sistema de libros y actualizar el catalogo cuando un libro sea prestado  |
| Características  | Muesta la aptutud para administar los libros y manejar que libro es prestado.  |
| Relaciones | Tiene dos realaciones con el actor usuario que son prestar libro y buscar libro  |
| Referencias | Buscar libro,Prestar libro,Actualizar catalogo |   
|  Notas |  Tiene que tener un conocimiento de los libros y de como actualizar el catalogo |
| Autor  | Joseph Vanegas Caicedo |
|Fecha | 31/01/2024 |

|  Caso de Uso	CU | Buscar libro  |
  |---|---|
  | Fuentes  | Jpexposito repositorio |
  | Actor  |  Usuario,Bibliotecario |
  | Descripción | El usuario o bibliotecario busca un libro en el catalogo  |
  | Flujo básico | 1.El usuaria va a el catalogo y pone el nombre del libro o un filtro. 2.El sistema devuelve la informacion que el usuario quiere |
  | Pre-condiciones | El usuario tiene que tener algo en mente que quiera leer o buscar para leer  |  
  | Post-condiciones  | Lo libros que se an buscado son  prestados  |  
  |  Requerimientos | el usuaria tiene que tener acceso al los libros que estan disponibles.  |
  |  Notas |  El sisteam hace busquedas avanzadas por criterios. |
| Autor  | Joseph Vanegas Caicedo |
|Fecha | 31/01/2024 |
  
  | Caso de Uso  | Prestar libros  |
|--------------|-----------------|
| Fuentes      | Sistema de préstamos  |
| Actor        | Bibliotecario  |
| Descripción  | Este caso de uso permite al bibliotecario gestionar los préstamos de libros realizados por los usuarios.  |
| Flujo básico | 1. El bibliotecario inicia sesión en el sistema. 2. Accede a la sección de gestión de préstamos. 3. Visualiza los préstamos activos y su estado. 4. Registra la devolución de libros. |
| Pre-condiciones  | El bibliotecario debe haber iniciado sesión y tener los permisos adecuados. |
| Post-condiciones | El sistema registra la devolución de libros y actualiza el estado de los préstamos.  |
| Requerimientos   | Conexión a la base de datos del sistema de biblioteca.  |
| Notas        | Se pueden generar multas por devoluciones tardías. |
  | Autor  | Joseph Vanegas Caicedo |
|Fecha | 31/01/2024 |

  | Caso de Uso (CU)    | Actualizar Catálogo                                              |
|----------------------|------------------------------------------------------------------|
| Fuentes              | Catálogo de la biblioteca, Sistema de inventario                 |
| Actor                | Bibliotecario                                                    |
| Descripción          | Este caso de uso permite al bibliotecario gestionar el catálogo de la biblioteca, incluyendo la adición, eliminación o actualización de información sobre los libros. |
| Flujo básico         | 1. El bibliotecario inicia sesión en el sistema. 2. Accede a la sección de gestión de catálogo. 3. Selecciona la opción de actualizar catálogo. 4. Agrega nuevos libros, actualiza detalles o elimina registros según sea necesario. |
| Pre-condiciones      | El bibliotecario ha iniciado sesión y tiene los permisos adecuados. |
| Post-condiciones     | El catálogo se actualiza según las modificaciones realizadas por el bibliotecario. |
| Requerimientos      | Conexión a la base de datos del sistema de biblioteca.           |
| Notas                | - Se puede incluir la capacidad de cargar información en formato de archivo para realizar actualizaciones masivas.<br> - El sistema puede generar registros de cambios para mantener un historial del catálogo. |
  | Autor  | Joseph Vanegas Caicedo |
|Fecha | 31/01/2024 |

  | Caso de Uso         | Devolver Libro                                                    |
|---------------------|-------------------------------------------------------------------|
| Fuentes             | Sistema de préstamos, Inventario de la biblioteca                 |
| Actor               | Usuario                                                           |
| Descripción         | Permite al usuario devolver un libro prestado por la biblioteca.  |
| Flujo básico        | 1. El usuario inicia sesión en el sistema.                       |
|                     | 2. Accede a la sección de "Mis Préstamos" o similar.             |
|                     | 3. Selecciona el libro a devolver.                               |
|                     | 4. Confirma la devolución.                                      |
|                     | 5. El sistema verifica y actualiza el estado del libro.          |
| Pre-condiciones     | El usuario ha iniciado sesión y tiene libros prestados.           |
| Post-condiciones    | El libro se registra como devuelto y se actualiza el estado del   |
|                     | préstamo en el sistema.                                          |
| Requerimientos      | El libro debe estar en buen estado para la devolución.            |
| Notas               | - Se pueden generar recordatorios automáticos para la devolución  |
|                     |   próxima.                                                        |
|                     | - Puede existir un período de gracia para devoluciones tardías   |
|                     |   antes de aplicar multas.   
  | Autor  | Joseph Vanegas Caicedo |
|Fecha | 31/01/2024 |

