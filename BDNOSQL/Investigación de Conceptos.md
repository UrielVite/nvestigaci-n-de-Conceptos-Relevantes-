Conceptos técnicos relacionados con bases de datos no relacionales y sus características.

1.- Escalabilidad Horizontal en NoSQL

Las bases de datos NoSQL están diseñadas para escalar horizontalmente, lo que significa que se pueden distribuir en múltiples servidores o nodos para manejar grandes volúmenes de datos y cargas de trabajo intensivas. Esto hace que las bases de datos NoSQL sean perfectas para entornos en cloud. En lugar de aumentar la potencia del servidor (escalabilidad vertical), puedes simplemente agregar más servidores al sistema para manejar cargas de trabajo más grandes.

![NoSQL](https://th.bing.com/th/id/OIG1.ujeG0391_3FPOq5Ck1z2?w=270&h=270&c=6&r=0&o=5&dpr=1.3&pid=ImgGn)

2.- Modelos de Consistencia en NoSQL

La consistencia eventual es un modelo de consistencia utilizado en los sistemas distribuidos, que permite que existan algunas formas de inconsistencia y garantiza que, con el tiempo suficiente, el sistema será consistente. La consistencia eventual se utiliza a menudo en sistemas donde la alta disponibilidad es más importante que la consistencia fuerte, como en las bases de datos distribuidas.

 Consistencia fuerte: La consistencia fuerte simplemente significa que los datos deben ser consistentes en todo momento. Todos los Nodes de servidor de todo el mundo deben contener el mismo valor que una entidad en cualquier momento. Y la única forma de implementar este comportamiento es bloquear los Nodes cuando se actualizan.

 Consistencia transaccional: Este tipo de consistencia se refiere a la capacidad de una base de datos para asegurar que una serie de operaciones se completen de manera atómica, consistente, aislada y duradera (ACID). En otras palabras, todas las operaciones dentro de una transacción se completan con éxito o ninguna lo hace, manteniendo la integridad de los datos.

![NoSQL](https://th.bing.com/th/id/OIG2.n9hFed.6WFm.wPz.iFd6?w=270&h=270&c=6&r=0&o=5&dpr=1.3&pid=ImgGn)

3.- MapReduce y su Uso en NoSQL

MapReduce es un modelo de programación y un marco de procesamiento de datos que fue diseñado para manejar grandes volúmenes de datos en un entorno distribuido, como clústeres de servidores. Este modelo fue popularizado por Google y se utiliza para procesar y generar grandes conjuntos de datos de manera eficiente.

Cómo funciona MapReduce:
Map:

En la fase de Map, se divide el conjunto de datos en fragmentos más pequeños.
A cada fragmento se le aplica una función map que transforma los datos en pares clave-valor.
El objetivo de esta fase es filtrar y organizar los datos. Cada mapper opera de manera independiente y en paralelo, lo que permite escalar el proceso a grandes volúmenes de datos.

Shuffle and Sort:

Los pares clave-valor generados por la función map son organizados y agrupados por su clave.
Esta fase es crítica para preparar los datos para la siguiente fase.

![NoSQL](https://th.bing.com/th/id/OIG3.fqUSgLFVKOnBTtoXqlp6?w=270&h=270&c=6&r=0&o=5&dpr=1.3&pid=ImgGn)

4.- Atomicidad y ACID vs BASE en NoSQL

Las propiedades ACID y el enfoque BASE representan dos enfoques distintos para manejar transacciones y consistencia en sistemas de bases de datos, especialmente en contextos donde se manejan grandes volúmenes de datos distribuidos.

Propiedades ACID (Atomicidad, Consistencia, Aislamiento, Durabilidad):
El modelo ACID es un conjunto de propiedades utilizadas en sistemas de bases de datos tradicionales, especialmente bases de datos relacionales, para garantizar la integridad de las transacciones.

Atomicidad:

Una transacción es una unidad indivisible. Si alguna parte de la transacción falla, toda la transacción se deshace, lo que garantiza que los datos permanezcan en un estado consistente.
Ejemplo: Si se transfiere dinero entre cuentas, ambas operaciones (debit y credit) deben completarse o ninguna lo hará.
Consistencia:

Una transacción lleva al sistema de un estado consistente a otro estado consistente. Las reglas de integridad de la base de datos no se violan en ningún punto.
Ejemplo: Si se actualiza una cuenta bancaria, el saldo no puede quedar negativo si no está permitido por las reglas del sistema.
Aislamiento:

Las transacciones concurrentes se ejecutan como si fueran secuenciales. No deberían interferir entre sí.
Ejemplo: Dos usuarios realizando operaciones en la misma cuenta no deberían ver resultados intermedios de las transacciones del otro.
Durabilidad:

Una vez que una transacción se ha completado, sus cambios son permanentes, incluso en caso de fallos del sistema.
Ejemplo: Si un sistema se apaga después de una transacción, los datos comprometidos deben persistir.

![NoSQL](https://th.bing.com/th/id/OIG1.LcQ0Q.6l6HNY1mAr0IZe?w=270&h=270&c=6&r=0&o=5&dpr=1.3&pid=ImgGn)



5.- Integración de NoSQL con Aplicaciones de Microservicios

Las bases de datos NoSQL se integran de manera natural con las arquitecturas de microservicios debido a su flexibilidad, escalabilidad, y capacidad para manejar grandes volúmenes de datos distribuidos. Esta integración permite a las organizaciones construir aplicaciones que pueden crecer y adaptarse rápidamente a las necesidades cambiantes del negocio.

Integración de NoSQL con Arquitecturas de Microservicios
Independencia de Microservicios y Bases de Datos:

En una arquitectura de microservicios, cada servicio es independiente y autónomo. Esto incluye la gestión de su propio almacenamiento de datos. Este enfoque se conoce como "database per service".
Las bases de datos NoSQL son adecuadas para este modelo porque permiten a cada microservicio elegir la base de datos que mejor se adapte a sus necesidades específicas, ya sea una base de datos de documentos, clave-valor, de grafos o de columnas.

Ventajas del Uso de NoSQL en Microservicios
Escalabilidad y Disponibilidad:

Al usar bases de datos NoSQL, los microservicios pueden aprovechar la capacidad de escalar horizontalmente, lo que permite manejar grandes volúmenes de datos y altos niveles de tráfico sin comprometer el rendimiento.
Además, muchas bases de datos NoSQL están diseñadas para ser altamente disponibles, lo que significa que pueden seguir operando incluso si algunos nodos fallan.


![NoSQL](https://th.bing.com/th/id/OIG4.TKJhVln3Um4bGkK3yOPw?w=270&h=270&c=6&r=0&o=5&dpr=1.3&pid=ImgGn)

6.- Indexación Secundaria en NoSQL

se refiere a la creación de índices en campos distintos de la clave primaria para acelerar las consultas que filtran datos usando esos campos. 

*Ejemplo*
En una base de datos NoSQL como MongoDB, si tienes una colección de documentos que representan usuarios con los campos userId, name y email, la clave primaria podría ser userId. 

*Cómo Funcionan*

Se implementan creando estructuras de datos adicionales (como árboles B o tablas hash) que mapean los valores de un campo específico a las ubicaciones de los documentos que contienen esos valores.

*Limitaciones*

- Rendimiento de Escritura:Puede afectar negativamente el rendimiento de las operaciones de escritura.

- Consistencia Eventual.

-  Escalabilidad.

Consumo de Espacio: En sistemas con grandes volúmenes de datos.

![NoSQL](https://th.bing.com/th/id/OIG3.FksrJeK.pY7vMQIvRqLo?w=270&h=270&c=6&r=0&o=5&dpr=1.3&pid=ImgGn)



7.- Comparación de Sistemas de Almacenamiento en NoSQL: SSD vs HDD


El tipo de almacenamiento, ya sea SSD (Solid State Drive) o HDD (Hard Disk Drive), tiene un impacto significativo en el rendimiento de las bases de datos NoSQL, que suelen manejar grandes volúmenes de datos y requieren acceso rápido para consultas y transacciones

**Capacidad de Almacenamiento:**

- SSD: Aunque la capacidad de los SSD ha aumentado, los HDD aún superan a los SSD en términos de almacenamiento máximo disponible, especialmente para volúmenes muy grandes de datos.

- HDD: Los HDD siguen siendo la opción preferida para almacenamiento masivo debido a su alta capacidad a un menor costo.

**Impacto en el Rendimiento de Bases de Datos NoSQL**

- El tipo de almacenamiento elegido puede influir considerablemente en las siguientes áreas de rendimiento de las bases de datos NoSQL:

- Tiempo de Respuesta de Consultas: Los SSD reducen  el tiempo de respuesta de las consultas, lo cual es crucial para aplicaciones que requieren respuestas en tiempo real.

- Rendimiento en Altas Cargas de Trabajo: Los SSD ofrecen un rendimiento superior en comparación con los HDD.

- Escalabilidad: Los HDD permiten escalar en capacidad de almacenamiento a un menor costo, los SSD permiten escalar en términos de rendimiento.

**Mejores Prácticas para la Elección del Almacenamiento**

- Evaluación de la Carga de Trabajo: Si la carga de trabajo involucra operaciones intensivas de lectura/escritura aleatorias o requiere baja latencia, los SSD son la opción preferida.

- Si la aplicación es más de tipo archivo o requiere almacenamiento masivo a bajo costo con operaciones predominantemente secuenciales, los HDD pueden ser suficientes.

- Consideraciones de Costo:

- SSD: Para aplicaciones críticas que requieren alto rendimiento.

- HDD: Para almacenamiento en frío o bases de datos que manejan grandes volúmenes de datos, los HDD ofrecen un costo más efectivo.

![Texto alternativo](https://th.bing.com/th/id/OIG3.Z27mLDclMEhf49mOVX2E?w=270&h=270&c=6&r=0&o=5&pid=ImgGn)


8.- Estrategias de Compresión de Datos en NoSQL

La compresión de datos en bases de datos NoSQL es una técnica clave para optimizar el uso del almacenamiento y mejorar el rendimiento general del sistema

Compresión Basada en Bloques: En esta técnica, los datos se dividen en bloques y cada bloque se comprime individualmente. 

Ejemplo:

- HBase: Utiliza compresión basada en bloques con algoritmos como GZIP y Snappy. Cada columna se comprime en bloques separados, lo que optimiza el acceso y la manipulación de datos comprimidos.

- Impacto: Mejora el rendimiento en operaciones de lectura porque solo se descomprimen los bloques necesarios. 

- Compresión de Columnas: Se aplica a los valores dentro de cada columna. Dado que los datos en una columna suelen ser homogéneos, la compresión es más eficiente.

**Ejemplo:**

- Cassandra: Utiliza compresión de columnas con algoritmos como LZ4 y Deflate, permitiendo que los datos dentro de cada columna sean comprimidos eficientemente.

- Impacto: Reduce significativamente el espacio en disco y puede mejorar el rendimiento de las consultas de lectura al minimizar la cantidad de datos que deben ser leídos desde el disco.


- Mejores Prácticas para la Compresión en NoSQL
Evaluar la Carga de Trabajo:

Analizar el tipo de datos y patrones de acceso antes de elegir una técnica de compresión. Por ejemplo, en sistemas de series temporales, la compresión delta puede ser más apropiada, mientras que la compresión de diccionarios puede ser mejor para datos textuales con alta redundancia.

![Texto alternativo](https://th.bing.com/th/id/OIG2.Yo9g5deaJEqzye.rFRdL?w=270&h=270&c=6&r=0&o=5&pid=ImgGn)


9.- Desempeño de NoSQL en la Nube vs On-Premises

**Latencia**

 On-Premises:

- Ventajas: La latencia es generalmente más baja en instalaciones locales.

- Limitaciones: La latencia puede ser afectada por la infraestructura interna, como la capacidad de la red o la saturación de los recursos del hardware.

Nube:
- Ventajas: La latencia puede ser baja si los recursos en la nube están geográficamente cerca de los usuarios finales o si se implementan en regiones optimizadas para baja latencia.

- Limitaciones: Las aplicaciones en la nube dependen de la conectividad a Internet.

 **Escalabilidad**

On-Premises:

- Ventajas: Escalabilidad controlada con la posibilidad de optimizar el hardware para necesidades específicas. 

- Limitaciones: La escalabilidad está limitada por la capacidad física disponible.


Nube:

- Ventajas: La nube ofrece escalabilidad casi instantánea y elástica.

- Limitaciones: Aunque la escalabilidad es más fácil, los costos pueden aumentar rápidamente si no se gestionan adecuadamente los recursos.

**Costos**

On-Premises:

- Ventajas: Los costos operativos son más predecibles y pueden ser más bajos a largo plazo.

- Limitaciones: Los costos iniciales son altos debido a la necesidad de adquirir hardware, software y contratar personal para el mantenimiento. 

Nube:

- Ventajas: Los costos son más flexibles y alineados con el uso real, gracias a modelos de pago por uso.

- Limitaciones: Los costos pueden ser impredecibles y subir rápidamente con el crecimiento del uso.

![Texto alternativo](https://th.bing.com/th/id/OIG4.fbzivVTHA3TIi1gGFMju?w=270&h=270&c=6&r=0&o=5&pid=ImgGn)



10.- Migración de SQL a NoSQL: Desafíos y Estrategias

**Desafíos Comunes**

Modelo de Datos Diferente

- SQL: Utiliza un modelo de datos relacional con tablas, filas y columnas. Las relaciones entre datos están normalizadas y se utilizan claves externas para mantener la integridad referencial.

- NoSQL: Utiliza varios modelos de datos (documentos, grafos, clave-valor, columnares), que son más flexibles pero pueden carecer de la estructura rígida y las relaciones definidas de las bases de datos relacionales.

- Desafío: Transformar un esquema de base de datos relacional en un modelo NoSQL sin perder integridad y consistencia puede ser complicado.

**Consistencia y ACID vs. BASE**

- SQL: Sigue el modelo ACID (Atomicidad, Consistencia, Aislamiento, Durabilidad) para transacciones, garantizando la consistencia de los datos.

- NoSQL: Sigue el modelo BASE (Básicamente Disponible, Estado Suave, Consistencia Eventual), que sacrifica algo de consistencia por disponibilidad y escalabilidad.
Desafío: Adaptarse a la eventual consistencia y diseñar la aplicación para manejar posibles inconsistencias temporales.

- Estrategias para Facilitar la Transición
Evaluación y Selección de la Base de Datos NoSQL

No todas las bases de datos NoSQL son iguales. Es importante seleccionar la que mejor se adapte a las necesidades de la aplicación (documento, clave-valor, grafo, columnares). 

**Migración Gradual**

En lugar de migrar todos los datos de una vez, comienza con un subconjunto de datos o con nuevas funcionalidades. Esto reduce riesgos y permite abordar problemas en fases controladas.

Rediseño del Modelo de Datos

Rediseña el modelo de datos teniendo en cuenta la naturaleza del almacenamiento NoSQL. 

Uso de Intermediarios o Abstracciones

Considera el uso de capas de abstracción que permitan a la aplicación seguir utilizando SQL mientras los datos se almacenan en NoSQL, o utiliza herramientas intermedias para facilitar la migración.

![Texto alternativo](https://th.bing.com/th/id/OIG1.tIgOVVXd_iYHRi6TYKws?w=270&h=270&c=6&r=0&o=5&pid=ImgGn)
