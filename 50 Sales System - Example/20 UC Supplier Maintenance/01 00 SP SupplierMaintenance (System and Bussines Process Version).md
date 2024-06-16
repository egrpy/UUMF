# Caso de Uso
# Supplier Maintenance

## Historial de Versiones
|Versión   | Fecha    | Acción                            |Responsables             |
|:--------:|:--------:|:----------------------------------|:------------------------|
|1.00      |01/02/2020|Versión inicial                    |(D) Roberto Pérez        |
|          |          |                                   |(C) Juan González        |
|1.01      |02/02/2020|Refinamiento                       |(D) Roberto Pérez        |
|          |          |                                   |(C) Juan González        |
|1.02      |02/02/2020|Interacción con CU Supplier Search |(D) Roberto Pérez        |

**_Nota:_**
* **Acción** debe indicar brévemente lo realizado.
* **Responsables** ¿quienes participaron de la redacción o modificación?, incluye a:
    * Personas del equipo de desarrollo (D)
    * Clientes (C)

## Descripción
Para que un proveedor (Suppliers) pueda realizar transacciones con la empresa, este debe estar registrado en el sistema.
Este caso de uso, permite al actor Logistic mantener la información de los proveedores (Suppliers) en el sistema.

## Actores
### Principal
* Logistic

### Secundario
* Supplier

## Relaciones con Casos de Uso
### Inclusión << include >>
* Ninguno

### Extensión << extend >>
* Caso de Uso Supplier Search
    * El proceso de mantenimiento de proveedores requiere que el usuario pueda buscar y seleccionar proveedores existentes.
        
### Generalización
* Ninguno

## Precondiciones
* Se requiere registrar un nuevo proveedor (Supplier), ó
* Se requiere editar y modficar los datos de un proveedor existente, ó
* Se requiere eliminar un proveedor, siempre que cumpla con las reglas de negocio

## Postcondiciones
La información del proveedor es actualizada, eliminada o agregada correctamente en el sistema.

## Flujo Principal
* El actor Logistic selecciona la opción de mantenimiento de proveedores
* Si el Id del proveedor no es conocido, el actor Logistic puede buscar un proveedor existente utilizando el CU Supplier Search
    * En caso de haber ejecutado el CU Supplier Search
        * El sistema asigna automáticamente el valor del Id del proveedor obtenido del portapapeles al atributo Id
* El actor Logistic ingresa o confirma el Id del proveedor
* El sistema busca la información del Id proporcionado
    * Si existe, muestra los datos obtenidos
        * Si se trata de una modificación de datos
            * El actor Logistic obtiene los datos a modificar del  actor Supplier
            * El actor Logistic actualiza los datos en sistema
            * El sistema valida los datos conforme a las regla de negocio para modificación 
            * El actor Logistic guarda los cambios
        * Si se trata de la eliminación del registro
            * El actor Logistic, elimina el registro
            * El sistema valida el cummplimiento de las reglas de negocio para eliminación
                * Si cumple con las reglas, el registro se elimina
                * Si no cumple con las reglas, se informa al actor Supplier
    * Si no existe
        * El sistema permite cargar un nuevo registro
        * El actor Logistic obtiene los datos del actor Supplier
        * El actor Logistic registra los datos en sistema
        * El sistema valida los datos conforme a las regla de negocio para nuevos proveedores
        * El actor Logistic guarda los cambios
"Si el Id del proveedor no es conocido, el actor Logistic puede buscar un proveedor existente utilizando el caso de uso Supplier Search. Una vez completada la búsqueda, el sistema asigna automáticamente el valor del Id del proveedor obtenido del portapapeles al campo correspondiente. Luego, el actor Logistic procede a ingresar o confirmar el Id del proveedor y el sistema continúa con la búsqueda de información del proveedor."



## Flujos Alternativos 
### Flujo Alternativo 1
* Si la validación de la información falla
    * El sistema muestra un mensaje de error indicando los datos incorrectos
    * El actor Logistic corrige los errores y vuelve a intentar guardar

### Flujo Alternativo 2
* Si el actor Logistic decide cancelar la operación
    * El actor Logistic selecciona la opción de cancelar
    * El sistema descarta los cambios y sale de la opción

## Reglas de Negocio
* Cada proveedor debe tener un Id único, y no es un dato modificable
* El email debe seguir el formato estándar de direcciones de correo electrónico
* No se puede eliminar un registro que tenga transacciones registradas

## Requisitos No Funcionales
* Eficiencia
    * El tiempo de respuesta para guardar los cambios debe ser menor a 2 segundos
* Claridad
    * Los mensajes de error deben ser explicitos
* Seguridad
    * Solo los usuarios con roles adecuados pueden realizar modificaciones
* Accesibilidad
    * La interfaz debe ser accesible para usuarios con discapacidades

## Validaciones Específicas
* Validar Unicidad del Id
    * Verificar unicidad del Id en la base de datos
* Validar Formato del Email
    * Utilizar expresión regular para asegurar formato correcto
* Validar Eliminación de Proveedor
    Comprobar que proveedor no tenga transacciones registradas antes de permitir eliminación
