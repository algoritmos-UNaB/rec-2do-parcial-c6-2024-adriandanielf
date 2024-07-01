[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/2Sch0d9F)
# recuperatorio-2dop-c6-2024

# 2do PARCIAL RECUPERATORIO LUNES 01/07/2024- Algoritmos y Estructuras de datos

## Modalidad:

- El parcial estará habilitado para su resolución desde: Lunes 01/07 @ 00:00hs, hasta: Lunes 01/07 @ 15:00hs. (pueden elegir cuando comenzar el intento)

- Tienen 1 (uno) sólo intento para resolver la actividad; el tiempo máximo es 4 (cuatro) horas.

- El tiempo será contabilizado desde el momento que aceptan realizar la actividad en Github Classroom, y cualquier "commit" realizado luego de 4 horas no será aceptado como parte del intento de resolución!!

NOTA: DEBEN COMPLETAR EL FINAL DE ESTE README CON SUS DATOS!!

# EJERCICIOS
## Ejercicio 1


Deben desarrollar una función que maneje un archivo de texto, con registros separados por comas. El mismo está compuesto de la siguiente manera:

dni;apellido;nombre;direccion;telefono;correo electrónico

El primer registro tiene los nombres de cada uno de los **datos**, es decir por ejemplo:

DNI;APELLIDO;NOMBRE;DIRECCIÓN;TELÉFONO;CORREO

Debe recorrer el archivo y recuperar los registros, para esto se tendrá que crear una función ***recuperarDatos(nombreArchivo)*** que:

1. Verifique que el archivo existe
2. Lea el primer registro para tomar los datos de cada campo
3. Leer los registros siguientes y confeccionar un string de la siguinte manera:

>"id = 1; nombre = abel; apellido = pintos; email = abel.pintos@gmail.com" salto de línea
>
>.
>
>.
>
>.
>
>ultimo dato


Luego guardar este texto en un nuevo archivo llamado *"datos_normalizados.txt"* en la carpeta *"/archivos_salida/"* donde solamente quedarán los registros que cumplan las siguientes condiciones:
- El DNI es un entero
- El correo electrónico contiene una @

**Consideraciones**:
- si el archivo existe el regitro 1 existe siempre
- puede no contener más registros luego del registro 1, en ese caso levantar un error que comunique con un mensaje al usuario
- la carpeta /archivos_salida/ puede existir o no y el archivo datos_planos.txt puede existir o no


## Ejercicio 2

### Sistema de Manejo de Filas Prioritarias para Acceso a Discos

Implementar unSistema de Manejo de Filas Prioritarias para Acceso a Discos.

Este sistema gestiona las solicitudes de acceso a discos, dando preferencia según el tipo de operación (lectura o escritura) y la prioridad. Consiste en tres clases principales:

- **Clase Fila**: Implementada como una lista enlazada para manejar solicitudes de acceso a discos, con métodos para agregar solicitudes, atender la siguiente solicitud y verificar si la fila está vacía.
- **Clase Disco**: Representa un disco individual, con métodos para obtener y cambiar su estado de disponibilidad.
- **Clase ManejadorListasAcceso**: Coordina el acceso a los discos, gestionando las filas de solicitudes y asignando discos disponibles. Incluye métodos para agregar solicitudes, atender solicitudes en orden de prioridad, liberar discos y realizar cálculos complejos sobre losdiscos disponibles.


### Definiciones
#### Clase Fila
La clase `Fila` se implementa como una lista enlazada que maneja las solicitudes de acceso a un disco. Cada nodo de la lista representa una solicitud y contiene la siguiente información:

- Tipo de operación (lectura o escritura)
- Prioridad de la solicitud (integer)
- Identificador único de la solicitud (integer)

Los métodos principales de la clase `Fila` son:

- `agregar_solicitud(tipo_operacion, prioridad)`: Agrega una nueva solicitud a la fila.
- `atender_siguiente()`: Retira y devuelve la siguiente solicitud de la fila.
- `esta_vacia()`: Verifica si la fila está vacía.

### Clase Disco
La clase `Disco` representa un disco individual y tiene los siguientes atributos y métodos:

- `disponible`: Indica si el disco está disponible u ocupado.
- `obtener_disponibilidad()`: Devuelve el estado de disponibilidad del disco.
- `marcar_como_disponible()`: Marca el disco como disponible.
- `marcar_como_ocupado()`: Marca el disco como ocupado.

### Clase Manejador de Listas de Acceso
La clase `ManejadorListasAcceso` coordina el acceso a los discos, gestionando las filas de solicitudes y asignando los discos disponibles a las solicitudes. Tiene los siguientes elementos:

- `fila_lectura`: Una instancia de la clase `Fila` que maneja las solicitudes de lectura.
- `fila_escritura`: Una instancia de la clase `Fila` que maneja las solicitudes de escritura.
- `discos`: Una lista circular de instancias de la clase `Disco`.

Los métodos principales de la clase `ManejadorListasAcceso` son:

- `agregar_solicitud(tipo_operacion, prioridad)`: Agrega una nueva solicitud a la fila correspondiente (lectura o escritura).
- `atender_siguiente_solicitud()`: Atiende la siguiente solicitud en la fila correspondiente, asignando un disco disponible si lo hay (debe primero revisar si hay pedidos de escritura, si no los hay puede entonces revisar la fila de lectura).
- `liberar_disco(disco)`: Marca un disco como disponible después de que se haya completado una solicitud.

El flujo de ejecución del sistema sería el siguiente:

1. Los usuarios realizan solicitudes de acceso a los discos, indicando el tipo de operación (lectura o escritura) y la prioridad.
2. El `ManejadorListasAcceso` recibe las solicitudes y las agrega a la fila correspondiente.
3. Periódicamente, el `ManejadorListasAcceso` llama al método `atender_siguiente_solicitud()` para procesar las solicitudes en orden de prioridad.
4. Si hay un disco disponible, se asigna a la solicitud y se marca como ocupado.
5. Cuando la solicitud se completa, el disco se marca como disponible mediante el método `liberar_disco()`.


### 2.1
Desarrollar lo anteriormente explicado

### 2.2

Implementar el ordenamiento por burbuja (Bubble Sort) en las filas, pueden hacerlo en la clase `Fila` o en la clase `ManejadorListasAcceso`.

Agregar el método: `ordenar_por_prioridad()`: Ordena la fila por prioridad utilizando el algoritmo de Bubble Sort.

> Ayuda: Este método recorre la lista enlazada, comparando la prioridad de cada nodo con la del siguiente. Si el nodo actual tiene una prioridad mayor que el siguiente, se intercambian los valores de prioridad y tipo de operación. El proceso se repite hasta que no se realicen más intercambios, lo que indica que la lista está ordenada.


### Resumen:
Finalmente las clases deberan ser: 

### Clase Fila
- `agregar_solicitud(tipo_operacion, prioridad)`: Completar
- `atender_siguiente()`: Completar
- `esta_vacia()`: Completar
- `ordenar_por_prioridad()`: Completar

### Clase Disco
- `disponible`: Completar
- `obtener_disponibilidad()`: Completar
- `marcar_como_disponible()`: Completar
- `marcar_como_ocupado()`: Completar

### Clase ManejadorListasAcceso
- `fila_lectura`: Completar
- `fila_escritura`: Completar
- `discos`: Completar
- `agregar_solicitud(tipo_operacion, prioridad)`: Completar
- `atender_siguiente_solicitud()`: Completar
- `liberar_disco(disco)`: Completar
- `contar_discos_disponibles()`: Completar
- `__iter__()`: Completar
- `__next__()`: Completar


## Ejercicio 3

### Preguntas Teóricas
1. Listas Enlazadas

Pregunta: ¿Qué es una lista enlazada; cuáles son sus principales ventajas y desventajas en comparación con las listas tradicionales?

2. Tiempos de Ordenamiento (Big-O)

Pregunta: ¿Cuál es la diferencia, en términos de complejidad temporal (Big-O), entre los algoritmos de ordenamiento Bubble Sort, Merge Sort y Quick Sort?

3. Biblioteca os en Python

Pregunta: ¿Qué funciones proporciona la biblioteca os en Python y para qué se utilizan comúnmente? Proporcione al menos tres ejemplos de funciones y sus usos.




*** 


### Datos:

- **Nombre Y Apellido:**
- **Email:**
- **Comisión:**




 
