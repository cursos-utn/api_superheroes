FORMAT: 1A

# API curso NodeJS
API REST para el manejo de superheroes.

# Group Superheroe

## Administrar superheroes [/superheroes]

### Obtener superheroes [GET]
Retorna el listado de superheroes registrados en el sistema

+ Request (application/json)

+ Response 200 (application/json)
    + Attributes (Listado Superheroes)

### Cargar nuevo superheroes [POST]
Registra un nuevo superheroe en el sistema

+ Request (application/json)
    + Attributes (Superheroe)

+ Response 200 (application/json)
    + Attributes (Respuesta Superheroe)
  
## Administrar un superheroe  [/superheroes/{id}]

  + Parameters
    + id: 1 (number) - Identificador del superheroe

### Obtener un superheroe [GET]

Retorna el listado de superheroes registrados en el sistema

+ Request (application/json)

+ Response 200 (application/json)
    + Attributes (Superheroe)

### Actualizar superheroe [PUT]
Actualiza los datos registrados de un superheroe

+ Request (application/json)
    + Attributes (Superheroe)

+ Response 200 (application/json)
    + Attributes (Respuesta Superheroe)


### Borrar superheroe [DELETE]
Borra los datos registrados de un superheroe

+ Request (application/json)

+ Response 200 (application/json)


# Data Structures

## Error Response (object)
+ status: `error` (string)
+ errors (array[Mensaje Error])

## Mensaje Error (object)
+ field: `nombre` (string) - Campo en el cual se produjo el error
+ error: `required` (string) - Que tipo de error se produjo en el campo

## Superheroe (object)
+ nombre: `Spiderman` (string)
    Nombre del superhéroe
+ superpoder: `Volar` (string)
    Superpoder principal
+ debilidad: `Kriptonita` (string)
    Punto débil del superhéroe
+ ejerciendo: `true` (boolean)
    Actualmente se encuentra ejerciendo


## Respuesta Superheroe (object)
+ status: `ok` (string)
    Mensaje que indica el resultado de la operacion (ok/error)
+ data (Superheroe)
    Superheroe guardado/actualizado

## Listado Superheroes (object)
+ status: `ok` (string)
    Mensaje que indica el resultado de la operacion (ok/error)
+ items (array[Superheroe])
