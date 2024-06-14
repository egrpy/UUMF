# Caso de Uso
# Supplier Search

## Historial de Versiones
|Versión   | Fecha    | Acción                            |Responsables             |
|:--------:|:--------:|:----------------------------------|:------------------------|
|1.00      |02/02/2020|Versión inicial                    |(D) Roberto Pérez        |

**_Nota:_**
* **Acción** debe indicar brévemente lo realizado.
* **Responsables** ¿quienes participaron de la redacción o modificación?, incluye a:
    * Personas del equipo de desarrollo (D)
    * Clientes (C)

## Descripción
Brinda la posibilidad de buscar un proveedor ingrsando una cadena de caracteres, la que será utilizada para buscar coincidencia con los valores de los atributos de Supplier.

## Actores
### Principal
* Logistic

### Secundario
* Ninguno

## Relaciones con Casos de Uso
### Inclusión << include >>
* Ninguno

### Extensión << extend >>
* Ninguno
        
### Generalización
* Ninguno

## Precondiciones
* Puede ser llamado por otros casos de uso
* Puede ser utilizado como una funcionalidad independiente sin ser llamado por otro caso de uso

## Postcondiciones
El sistema muestra una lista de proveedores que coinciden con los criterios de búsqueda especificados.

## Flujo Principal
* El actor Logistic selecciona la opción de búsqueda de proveedores
* El sistema presenta un formulario de búsqueda de proveedores
* El actor Logistic ingresa los criterios de búsqueda (por ejemplo, nombre, dirección, etc.)
* El sistema realiza la búsqueda basada en los criterios ingresados
* El sistema muestra una lista de proveedores que coinciden con los criterios de búsqueda
* Si el actor Logistic selecciona uno de los registros de la lista
    * El sistema guarda el valor del Id Supplier seleccionado en el portapapeles para su uso posterior

## Flujos Alternativos 
### Flujo Alternativo 1
* Si no se encuentran proveedores que coincidan con los criterios de búsqueda ingresados
    * El sistema muestra un mensaje indicando que no se encontraron resultados.

### Flujo Alternativo 2
* Si el actor Logistic decide cancelar la operación de búsqueda
    * El actor Logistic selecciona la opción de cancelar.
    * El sistema descarta los criterios de búsqueda y sale de la opción.

## Reglas de Negocio
* Ninguna específica para este caso de uso

## Requisitos No Funcionales
* Eficiencia
    * La búsqueda de proveedores debe ser rápida y eficiente, responder en menos de 2 segunddos
* Usabilidad
    * La búsqueda de proveedores debe ser rápida y eficiente.

## Validaciones Específicas
* Validar que los criterios de búsqueda en nombre, dirección e email tengan al menos 2 caracteres contiguos (sin espacios)
    * Si no se cumple este requisito, el sistema mostrará un mensaje de error indicando que los criterios de búsqueda deben tener al menos 2 caracteres consecutivos.
