---
tags:
  - PUC
  - APUNTES
url:
---
Tags: [[PUC]], [[APUNTES]]

	Este apunte es más que nada para estudiar para el midterm, sería una especie de resumen de la materia que entra, sea de las clases o de los contenidos. (Año 2024). - Rafa L
# Midterm

## Semana 02

### Guía de estilo
PEP8. En el caso del curso, las reglas que seguirá el curso:
- Uso de **snake_case** --> " _ " para variables, funciones, métodos...
- Uso de **CamelCase** para nombres de clases
- Usar nombres descriptivos (no xd = variable).
- *Imports* al comienzo del archivo
- Espacio después de comas
- Espacios a cada lado de operadores ( + - / * )
- Usar 4 espacios para indentar. (Igualmente uso tabs, no me maten)
- Líneas de máximo 100 caracteres o "100 columnas".
- Máximo 400 líneas (No es PEP8, pero se usa en el curso)

### Git
Los únicos comandos importantes son: `clone`, `pull`, `add`, `commit` y `push`, los cuales se usan en la terminal. 
`clone`: Sirve para clonar un repositorio (remoto) a una carpeta en tu dispositivo (local).
`pull`: Si hay un cambio en el repo remoto, entonces con git pull actualizas los cambios que se hicieron en en el repo remoto para verlos en el local. (Se usa más que nada para "pullear" las tareas, actividades, contenidos, etc).
`add`: Añade un archivo a la "staging area" es como para decir que queremos subir x archivo. `git add --all` para añadir todos los archivos con cambios.
`commit`: Crea una versión del archivo que existe en el staging area. `git commit -m "mensaje"` para escribir un mensaje o poner una descripción/nota de la versión. Estos archivos existen en nuestro repo local.
`push`: Sube los commits al repo remoto.

## Semana 03
### Estructuras de datos
**Estructuras secuenciales**
Garantizan un recorrido ordenado y eficiente de los elementos. Algunos ejemplos:
- Tuplas, *Named tuples*, Listas, Stacks, Colas

**Estructuras no secuenciales**
No hay orden de elementos, búsqueda es muy eficiente. Ejemplos:
- Sets, Diccionarios, *Defaultdict*

`Sets`: Solo permite elementos inmutables y no permite elementos duplicados.  {"set"}. No hay orden
`Diccionarios`: Almacena pares key-value. Las llaves no pueden ser duplicadas, ni mutables. Valor puede ser cualquier cosa. ["Dict"].
`Tuplas`: Orden secuencial de elementos, búsqueda eficiente del elemento i-ésimo. **Immutable**. Suele utilizarse para agrupar elementos heterogéneos. Ej: curso = ("IIC2233", 3, "2024-2", 58390, 90, profesores), con profesores una lista.
`Named tuples`: Se usan mucho en el curso. Orden secuencial de elementos, busqueda de i-ésimo elemento muy eficiente, immutable. **Cada posición tiene un nombre (atributo)**. Para usarlas se hace un import: from **collections** import *namedtuple*. Ej: Planta = namedtuple('Nombre', 'cantidad', 'color', 'disponibilidad'). c = Planta('Cactus', 6, 'verde', True).
Si quedemos acceder por ejemplo a la cantidad se puede hacer: c[1] o c.cantidad .
`Stacks`: Orden secuencial de elementos, mutable y con métodos append y pop, pero se elimina el último elemento. LIFO: Last in - First out. Se usa en navegadores web.
stack = [], stack.append(1), stack.append(2) == stack = [1, 2]. stack.pop() == stack = [1]
`Colas`: Para usarlas se tiene que hacer el import: from **collections** import *deque*. Mutable y 
eficiente en ambos extremos. append y appendleft -> appendea al inicio.  FIFO: First in - First out. 

### Desempaquetamiento
realizable con el operador asterisco, sirven para desempaquetar estructuras secuenciales ( * ) como una llave de valor ( ** ).

`*args`: Para argumentos posicionales. func(`*args`), con args una lista o tupla. (iterables)

`**kwargs`: Para pares llave-valor. func(`**kwargs`), con kwargs un diccionario

Ejemplos:
def ejemplo(a, b, c):
    print(f'a: {a}, b: {b}, c: {c}')
    
ejemplo('hola', `*['mundo', 42]`) -> a: hola, b: mundo, c: 42
ejemplo(`*['hola', 'mundo'], *[42]`) -> a: hola, b: mundo, c: 42
ejemplo(`*['hola', 'mundo'], **{'c': 42}`) -> a: hola, b: mundo, c: 42
ejemplo(`*['hola'], **{'c': 42}, **{'b': 'mundo'}`) -> a: hola, b: mundo, c: 42


## Semana 04
### OOP mas pro
**Herencia**: Nos permite claramente heredar datos de una clase y utilizarlos en otra. Se especifica de la forma `class 'Nombre superclase'` ... Después si una clase hereda de la anterior: `class 'Nombre clase hija(Nombre superclase)'`.  La herencia también nos permite sobreescribir métodos de la clase madre, lo que se conoce como *overriding*. Utilizando el método super() podemos utilizar la implementación de un método de la superclase sin nombrar explícitamente a la clase superior.

**Polimorfismo**:

## Semana 06
### Excepciones
**SyntaxError**: Ocurre si una sentencia del programa está mal escrita y viola sus reglas sintácticas. Ej: print "Hola Mundo" o for i in range(9) --> expected ":".
**IndentationError**: Hereda de SyntaxError, se genera cuando eciste una línea con incorrecta indentación. Casi siempre viene después de un if, else, def....
**NameError**: Ocurre cuando no se encuentra una declaración global o local de un nombre o función.
**ZeroDivisionError**: Self explanatory.
**IndexError**: Cuando existe una indecaxión fuera de rango. Ej: edad = (36, 21, 12). edad[3] <- mal indec, out of range.
**KeyError**: Cuando se entrega una key inválida trabajando con diccionarios o mapping.
**AttributeError**: Uso incorrecto de métodos o atributos en clases.
**TypeError**: Manejo erróneo de tipos de datos. Ej: 2 + [25, 7, 44] <- unsupported operand for +: 'int' and 'list'. O también: cantidad = 83.  cantidad() <- TypeError, 'int' not callable.
**ValueError**: Manejo erróneo del valor de los datos. Ej:
"Mi string separable por espacios".split(" ") <- Bien
"Mi string separable por espacios".split("") <- Mal, valor "" no está separado. O también: lista = [1, 2, 3, 4, 5]
lista.remove(6) <- ValueError

## Semana 09
### Threading
import `threading`
Correr simultáneamente varias instrucciones. **Proceso**: Programa en ejecución que ocupa un espacio en la memoria RAM del computador y ejecuta un flujo de instrucciones. CPU -> Posee núcleos (cores) que leen instrucciones de los programas que se ejecutan. Pueden haber varios procesos ejecutándose de manera simultánea, también hay procesos que se ponen en cola, esperando para usar un núcleo.

**Thread**: Unidad de ejecución de código dentro de un proceso. Lleva un registro de variables locales y en que parte del código del programa se encuentra. 
*Thread scheduling / time slicing*:
1. Se escoge un thread para ejecutar.
2. Se ejecuta un cierto número de instrucciones de ese thread o durante cierto tiempo.
3. Se deja el thread actual en espera.
4. Se vuelve al paso 1.

Un núcleo -> Más lento porque hay que controlar el tiempo, pero más claro ya que no se programa el salto entre aspectos del programa.

Clase `Thread` representa un hilo, se le entrega una función, la que recibe en el parámetro `target` al crear el thread. Para ejecutar un thread se llama al método `start()`. Una vez ejecutados, para volver a ejecutarlos hay que volver a instanciar el thread. 

Podemos también crear clases que herenden de la clase `Thread`, estas clases serán threads con comportamiento común y se tiene que hacer override del método `run()` el cual se ejecuta cuando se llama a start.

SI necesitamos que el programa principal termine la ejecución de algún thread o grupo de threads debemos usar el métoto `join(timeout=None)`. Con este método el MainThread(o cualquier otro que use join) queda bloqueado hasta que los threads referenciados terminen o espera n segundos especificados en timeout=n. 

Para ver si un thread sigue en funcionamiento se puede usar el método `is_alive()`. Se usa normalmente después de un join.

#### Daemons
Los **daemon threads** son aquellos que terminan el programa principal a pesar de que estén corriendo. Si no existieran tendríamos que esperar a que los threads terminen todos para que el programa principal pueda terminar. Si el programa termina -> Daemon threads mueren. Se especifican de la forma `daemon = True` en el constructor del thread.

#### Concurrencia
Queda la cagá, a veces intentamos modificar al mismo tiempo un mismo valor con dos threads distintos, pero recordemos:
- Las operaciones de los threads pueden ser pausadas para dar paso a otro thread.
- Es imposible saber como se entremezcla la ejecución de threads.
Operación **atómica**: Un solo thread puede iniciarla si ningún otro la está ejecutando. **Sección crítica**: conjunto de instrucciones atómicas. Cómo coordinamos o sincronizamos los threads?

`Lock`: Se utiliza pa que solo 1 thread esté en una misma sección crítica. Si un thread quiere acceder a la s.c, debe obtener el *lock* mediante `acquire()`. Cuando adquiere el *lock*, lo bloquea, imposibilitando su adquisición para otros threads. Cuando el thread bloqueado quiera salir, se usa `release()`. 

## Semana 10
### Serialización 

### Manejo de bytes
El computador solo puede guardar ceros y unos, por lo que lo hace en formato de *Byte*, secuencias de 9 bits donde un bit es un valor 0 ó 1. Una codificación muy común es la [ASCII](https://es.wikipedia.org/wiki/ASCII). Para obtener el caracter correspondiente a un código utilizamos la función `chr(número)` y para obtener el código correspondiente a un caracter `ord('volaita')`.

Es común igualmente usar la notación **hexadecimal** para representar bytes (0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F). Para reconocer una representación hexadecimal se suele anteponer el string `0x`, por ejemplo:
```python
for i in [0, 8, 12, 15, 16, 42, 100, 255]:

    print(f"Decimal: {i}, Hexadecimal: {hex(i)}")

# Decimal: 0, Hexadecimal: 0x0
# Decimal: 8, Hexadecimal: 0x8
# Decimal: 12, Hexadecimal: 0xc
...
```

#### El objeto bytes y bytearray
En python es un un objeto **inmutable** como los str, para declarar que un objeto es un byte, se antepone al comienzo del objeto una `b`:
$$ \text{caracteres = b"\x63\x6c\x69\x63\x68\xe9"}$$
Para codificar un string en un alfabeto específico utilizamos el método `encode`.

Los *bytearrays* son listas de bytes que sí son mutables. Se puede aplicar todo lo de listas, eso sí se tiene que añadir a un bytearray con el método `extend(byte)`, append solo funciona con ints.

**Chunks**: Grupo de bytes. Importante para leer una cantidad grande de bytes.
**Byteorder**: Cómo se representan cosas muy grandes? (1 byte se puede representar por un número de 0 a 255), si quisieramos representar el 256:
- Big endian: El byte más significativo queda al inicio del byte. 256 -> \x01 \x00.
- Little endian: El byte más significativo queda al final del byte. 256 -> \x00 \x01.


## Semana 12
### Interfaces gráficas

GUI: Graphical user interface.  ¿Como proveemos este tipo de información? *polling* -> Revisar activamente cada elemento de la interfaz con un while.

**Evento**: Acción que ocurre en el programa. Por ej:
- Hacer click en botón 1
- El mouse se encuentra sobre una imagen
Entonces, para cada evento `e` definimos una función `e_handler`, que se ejecutará cada vez que ocurra el evento `e`.

#### PyQt
Framework multi-plataforma que permite construir GUI, basado en C++Qt. Se encuentra dividida en un conjunto de módulos:
- **QtWidgets**: contiene las clases que brindan los elementos clásicos de interfaces gráficas para aplicaciones en _desktop_ PCs.
- **QtCore**: incluye las clases para funcionalidades no-GUI, como: ciclo de eventos, manejo de archivos, tiempo, _threads_, etc.
- **QtGui**: contiene las classes con componentes para integración de ventanas, manejo de eventos, etc.
- **QtNetwork**: provee las clases para crear aplicaciones gráficas en entornos de red basadas en TCP/IP, UDP.
- **QtOpenGL**: incluye las clases para el uso de OpenGL durante renderizado 3D.
- **QtSvg**: provee de clases para mostrar archivos de gráficos vectoriales (SVG).
- **QtSql**: incluye funcionalidades para el trabajo con bases de datos SQL.
- **QtBluetooth**: contiene clases que permiten la búsqueda e interacción con dispositivos a través de Bluetooth.

**Crear una ventana**
Usamos la clase `QWidget` desde `QtWidgets`. Tenemos que crear la aplicación que contendrá la ventana y sus widgets con `QApplication`: Recibe como argumento parámetros que son entregados desde la cmd. La clase QWidget representa un elemento gráfico y es la clase de todos los objetos de la interfaz. Esta puede recibir todos los eventos del sistema y puede mostrar una representación en la pantalla.

**Debuggeo**
```python

if __name__ == '__main__':

    def hook(type, value, traceback) -> None:

        print(type)

        print(traceback)

    sys.__excepthook__ = hook

  

    app = QtWidgets.QApplication([])

    ventana = MiVentana(*args)

    ventana.show()

    sys.exit(app.exec())

#Cortesía de Felipe Pezoa, 2017.
```

**Sistema coordenado**
 `setGeometry`: posición horizontal esquina superior izq, posición vertical esquina superior izq, ancho, alto. 
 La pantalla es arriba a la izquierda (0,0), abajo a la derecha (1600,900).
 
##### Widgets

El método **init_gui** se crea el widget principal y se posicionan las diversas instancias como:
`QLabel`: Desplegar texto. `QLineEdit`: Cuadros de texto (reciben texto).  Ambos se instancian con el texto que contienen (puede ser vacío ' ') y también con su propia geometría utilizando el método move y setGeometry.
`QPixMap`: Carga imágenes como pixeles, se tiene que crear la instancia con la ruta de la imágen.
`QPushButton`: Para crear botones. Cuando se instancia se suele usar QPushButton('&Texto', self) el & es pa destacar la primera letra.
`Layouts`: Lo malo del move y setGeometry es que no se modifica el tamaño del widget si se cambia el tamaño de la ventana, la app se vería distinta para diferentes plataformas o configuraciones. Existen dos tipos de layouts: ```QHBoxLayout``` y ```QVBoxLayout``` El primero para ponerlos en horizontal y el segundo en vertical.
Otro tipo de layout es el `QGridLayout`.

#### Eventos y señales
`exec()`: aplicación empieza a detectar eventos una vez que ha entrado en su main loop. 
Mecanismo signal (emitir una señal) a la ranura (slot) correspondiente. Mediante `connect()` se establece la comunicación. 

`sender()`: Obtener el emisor de una señal. 
Existen señales redeterminadas de mouse y teclado, sin embargo tambien se pueden personalizar y crear señales (como atributos) subclase de `QtCore.Qobject`. Con el método `emit` se emite la señal y con `connect` se define la función a ejecutar.

#### Diseño de software
- El ***front-end*** está relacionado a la **interfaz gráfica** con la cual el usuario interactúa, y
- El ***back-end*** se refiere a la **lógica** detrás de ella.

## Semana 14
### Qthreads
Parecidos a los del módulo threading, pero son más compatibles con PyQt ya que pueden tener señales definidas como atributos de clase. También está el objeto `QMutex` que funciona como el lock.

---


###### Referencias:
Syllabus y contenidos de clase. 
