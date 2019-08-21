FORMAT: 1A

# API curso NodeJS - Final
API REST para el manejo de agenda.

# Group Agenda

## Administrar contactos [/contactos]

### Obtener contactos [GET]
Retorna el listado de contactos

+ Request (application/json)

+ Response 200 (application/json)
    + Attributes (Listado Contactos)

### Cargar nuevo contacto [POST]
Agrega un contacto

+ Request (application/json)
    + Attributes (Contacto)

+ Response 200 (application/json)
    + Attributes (Respuesta Contacto)
  
## Administración de un contacto  [/contactos/{id}]

  + Parameters
    + id: 1 (number) - Identificador del contacto

### Obtener un contacto [GET]

Retorna un contacto (cuyo id es pasado como parámetro)

+ Request (application/json)

+ Response 200 (application/json)
    + Attributes (Contacto Unico)

### Actualizar contacto [PUT]
Actualiza los datos de un contacto

+ Request (application/json)
    + Attributes (Contacto)

+ Response 200 (application/json)
    + Attributes (Respuesta Contacto)


### Borrar contacto [DELETE]
Borra un contacto

+ Request (application/json)

+ Response 200 (application/json)


# Data Structures

## Error Response (object)
+ status: `error` (string)
+ errors (array[Mensaje Error])

## Mensaje Error (object)
+ field: `nombre` (string) - Campo en el cual se produjo el error
+ error: `required` (string) - Que tipo de error se produjo en el campo

## Contacto (object)
+ nombre: `Juan` (string)
    Nombre del contacto
+ apellido: `Perez` (string)
    Apellido del contacto
+ telefono: `11223344` (string)
    Número de teléfono del contacto
+ email: `mi_contacto@gmail.com` (string)
    E-mail del contacto
+ ciudad: `Remedios de Escalada` (string)
    Ciudad del contacto
+ provincia: `Buenos Aires` (string)
    Provincia del contacto
+ pais: `Argentina` (string)
    País del contacto

## Contacto Unico (Contacto)
+ temperatura: `22.3` (string)
    Temperatura en la ciudad del contacto

## Respuesta Contacto (object)
+ status: `ok` (string)
    Mensaje que indica el resultado de la operacion (ok/error)
+ data (Contacto)
    Contacto guardado/actualizado

## Listado Contactos (object)
+ status: `ok` (string)
    Mensaje que indica el resultado de la operacion (ok/error)
+ items (array[Contacto])
