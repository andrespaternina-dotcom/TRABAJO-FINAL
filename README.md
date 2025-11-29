# TRABAJO-FINAL
## Integrantes
- Isabel Ramirez Sanchez
- Mayra Yulitza Roa Lesmes
- Yomar Andres Patenina Agustin
  
## <font color='157699'> **Vínculos académicos y descripción** </font>
| Nombre | Carrera	| Habilidades | Fortalezas | Edad | Seccional | Semestre | Expectativas con el curso |
|:---|:---|:---|:---|:---|:---|:---|:---|
| Isabel Ramirez Sanchez | Ingeniería Industrial	| Organización	| Adaptabilidad	| 21 | Oriente | 5to | Aprender mucho sobre la programación, adquirir conocimientos, conocer su historia y su importancia.|
| Mayra Yulitza Roa Lesmes | Ingeniería Industrial	| Comunicación	| Creatividad	| 27 | Medellín | 6to | Aprender la sintaxis básica de un lenguaje de programación como lo es Python. Enfrentarme al miedo de no saber programar cosas básicas porque no tengo ningún conocimiento de programación. Y practicar bastante para comprender mejor los temas.|
| Yomar Andres Patenina Agustin | Ingeniería Industrial	| Aprendizaje Continuo	| Análisis	| 23 | Bajo Cauca | 6to | Iniciar la carrera hacia una programación avanzada con Python, a través de las bases y principios fundamentales que espero conocer de esta, y que a su vez servirán como cautivador para profundizar y especializarme más en este mundo.|

## Nombre del proyecto y detalles (El proyector de la UdeA)

Espacio distinado a ofrecer una experiencia cinematográfica única y acogedora en el Corazón de la UdeA, donde estudiantes, profesores, 
y comunidad en general puedan disfrutar de películas de alta calidad, reflexionar sobre temas relevantes y conectarse con otros a través del cine.

Si buscas un lugar para relajarte después de una semana de estudio, aprender algo nuevo o simplemente conectar con otros a través del cine, ¡El Proyector de la UdeA es tu lugar!

## Licencia del software

La licencia que se ha definido para el registro del software es "MIT License".

## Reporte de visión
Una plataforma digital de gestión para el proyecto El Proyector de la U, diseñada para facilitar todas las actividades relacionadas con la proyección de cine en la Universidad de Antioquia: programación de películas, venta de entradas, promoción de funciones, control de asistencia, retroalimentación del público y generación de reportes para los organizadores.

Objetivos

*   Automatizar la organización de funciones (selección de película, horarios, salas) para reducir errores manuales.
*   Facilitar al público universitario la compra de entradas con anticipación y acceso digital (QR, comprobantes).
*   Controlar la transparencia financiera mediante reportes de ingresos, costes y asistencia.
*   Mejorar la experiencia del usuario final a través de interfaz intuitiva, comunicación clara sobre el evento y participación mediante retroalimentación.
*   Permitir al equipo organizador tomar decisiones informadas usando datos reales (asistencia, satisfacción, costos).

Beneficios

*   Ahorro de tiempo y esfuerzo del equipo organizador, al evitar gestiones manuales (listas, boletos físicos, seguimiento manual).
*   Mejor convocatoria, al permitir promoción digital, notificaciones y visibilidad del calendario de funciones.
*   Mayor satisfacción del público, al ofrecer comodidad de compra y claridad.
*   Sostenibilidad del proyecto al poder planificar basado en datos reales (qué películas tienen mejor asistencia, qué horarios funcionan mejor).
*   Posible expansión futura del proyecto aprovechando la infraestructura digital, con menos barreras logísticas.

## Especificación de requisitos

**Requisitos Funcionales (RF): Son las acciones específicas que el sistema debe realizar.**

RF1. Registro de usuarios:
* El sistema debe permitir registrar usuarios solicitando: nombre, apellido, documento y tipo de vínculo con la Universidad.
* El sistema debe validar que los datos no estén vacíos, que el nombre y apellido no contengan dígitos y que el documento sea numérico y esté en el rango permitido.
* El sistema debe impedir registrar un documento duplicado.

RF2. Gestión del tipo de vínculo:
* El sistema debe asignar automáticamente el precio de la boleta según el tipo de vínculo: estudiante, docente, administrativo, oficial o externo.

RF3. Consulta de funciones del fin de semana
* El sistema debe mostrar las funciones disponibles (sábado y domingo) indicando: día, hora, título y sala.
* El sistema debe calcular y mostrar la cantidad de sillas disponibles para cada función.

RF4. Visualización del mapa de asientos:
* El sistema debe mostrar una matriz de 11x11 con el estado de cada asiento:
“O” → asiento disponible
“X” → asiento reservado
* Las filas deben identificarse con letras (A–K) y las columnas con números (1–11).

RF5. Crear reservas (compra de entradas):
* El usuario registrado debe poder seleccionar una función y un asiento disponible.
* El sistema debe verificar disponibilidad antes de confirmar la reserva.
* El sistema debe generar un ID único de reserva.
* El sistema debe emitir una factura simple con: nombre del usuario, precio pagado y asiento seleccionado.
* El asiento debe cambiar de estado de “O” a “X”.

RF6. Cancelación de reservas:
* El usuario debe poder cancelar una reserva activa ingresando su documento y el ID de la reserva.
* El asiento debe cambiar nuevamente a “O”.
* El usuario no podrá cancelar reservas de otros usuarios.

RF7. Acceso administrador:
* El sistema debe permitir que el administrador ingrese con usuario y contraseña para ver reportes.
* Las credenciales deben verificarse.

RF8. Reportes del administrador:
* El sistema debe mostrar:
Total de reservas registradas (incluye canceladas).
Total de reservas activas.
Total pagado por las reservas activas.
Promedio de venta por ticket.
Usuario con mayor número de reservas.
Usuario con menor número de reservas.
Listado de usuarios con su número de reservas.

RF9. Exportación a CSV:
* El sistema debe exportar a archivos .csv la información de usuarios y reservas.
* Debe crear automáticamente la carpeta export/ si no existe.


**Requisitos No Funcionales (RNF): Estos describen cualidades, restricciones y criterios de calidad del sistema.**

RNF1. Usabilidad:
* La interfaz debe ser completamente textual e intuitiva.
* Los menús deben mostrar opciones numeradas.
* Los mensajes deben guiar al usuario de manera clara y directa.

RNF2. Rendimiento:
* El sistema debe responder de forma inmediata a las solicitudes del usuario.
* La búsqueda de usuarios, asientos y reservas debe ejecutarse en tiempo constante o cercano (uso de diccionarios y listas optimizadas).

RNF3. Confiabilidad:
* El sistema debe manejar entradas incorrectas sin cerrarse inesperadamente.
* La información de asientos reservados debe mantenerse coherente incluso en cancelaciones.

RNF4. Seguridad:
* El módulo de administrador debe requerir autenticación con usuario y contraseña.
* Las contraseñas no deben mostrarse mientras son digitadas (uso de getpass).
* Los datos exportados deben respetar la integridad del formato.

RNF5. Portabilidad:
* El sistema debe ejecutarse correctamente en cualquier entorno que soporte Python 3.x (Google Colab, Windows, Linux, Mac).
* No debe depender de librerías externas que no estén en la biblioteca estándar de Python.

RNF6. Mantenibilidad:
* El código debe estar modularizado usando clases y funciones.
* Las responsabilidades deben estar claramente separadas: usuarios, reserva, administración.
* El código debe incluir comentarios que faciliten comprensión y futuras ampliaciones.

RNF7. Compatibilidad:
* Los archivos CSV generados deben ser compatibles con Excel, LibreOffice y Google Sheets.
* El sistema debe ser compatible con el flujo de uso del repositorio GitHub según lo pedido en el PDF.

RNF8. Escalabilidad:
* La estructura de clases debe permitir agregar más salas o más funciones sin reescribir completamente el sistema.
* El manejo de asientos debe permitir ampliar la matriz si el número de sillas cambia.

## Plan de proyecto
La descripción de las actividades, el cronograma y el presupuesto con horas programadas se encuentra en el archivo de excel "Presupuesto cinema".

## Manual de usuario

##<font color='0416ef'> **Descripción general** </font>

EL PROYECTOR DE LA UdeA es un programa de consola desarrollado en Python que simula la gestión básica de un cine universitario.
El sistema permite registrar usuarios, consultar funciones del fin de semana, reservar asientos, cancelar reservas, generar reportes administrativos y exportar datos en formato CSV.

Toda la interacción se realiza mediante menús en consola.
<font color='0416ef'> **Características principales** </font>

*   Registro de usuarios con validaciones automáticas.
*   Consulta de funciones del fin de semana.
*   Visualización del mapa de asientos (11×11).
*   Reserva y cancelación de asientos por documento.
*   Cálculo automático del precio según tipo de vínculo.
*   Reporte administrativo completo: ingresos, reservas, usuarios.
*   Exportación de datos en archivos CSV.
*   Control de acceso para administradores.

<font color='0416ef'> **¿Cómo ejecutar el sistema?** </font>

Abrir y ejecutar el archivo Python / notebook donde se encuentra el código.

Ejecutar todas las celdas (si está en Colab o Jupyter).

El sistema mostrará el menú principal para comenzar la interacción

📁 Estructura recomendada del proyecto
el_proyector_udea/
│── main.py  (o .ipynb)
│
└── export/           # Se genera automáticamente al exportar CSV
    ├── usuarios.csv
    └── reservas.csv

<font color='0416ef'> **Registro de usuarios** </font>

El sistema solicita:

*   Nombre y apellido
*   Documento de identificación

Tipo de vínculo:

estudiante

*   Docente
*   Administrativo
*   Oficial
*   Externo

El precio de la boleta se calcula automáticamente según el vínculo, así:

Tipo de vínculo	Precio

*   Estudiante	7500
*   Docente	10000
*   Administrativo	8500
*   Oficial	7000
*   Externo	15000

<font color='0416ef'> **Validaciones aplicadas** </font>

*   Nombre y apellido deben tener mínimo 3 letras y no contener números.
*   El documento debe ser numérico y tener entre 3 y 15 dígitos.
*   El tipo de vínculo debe coincidir con las categorías válidas.
*   El usuario no debe estar registrado previamente.

<font color='0416ef'> **Funciones del fin de semana** </font>

El sistema incluye 4 funciones programadas:

1. Sábado 16:00 - Cine Clásico I - Sala A
2. Sábado 19:00 - Cine Contemporáneo - Sala A
3. Domingo 15:00 - Documental UdeA - Sala B
4. Domingo 18:00 - Comedia Universitaria - Sala B

El sistema muestra: ID, Día, Hora, Título y Número de sillas disponibles.

<font color='0416ef'> **Mapa de asientos** </font>

El cine dispone de 121 sillas (11 filas x 11 columnas).

Filas representadas por letras A–K.

Columnas 1–11.

Donde:

    ✔ O = asiento libre
    ❌ X = asiento ocupado

<font color='0416ef'> **Reserva de asientos** </font>

Para reservar:
*   Ingresar documento del usuario.
*   Ver funciones disponibles.
*   Seleccionar ID de la película.
*   Ver mapa de sillas.
*   Elegir asiento (ej. B 7).

**Validaciones:**

*   El usuario debe estar registrado.
*   El asiento debe existir.
*   El asiento debe estar disponible.

**El sistema genera:**

*   ID de la reserva
*   Precio según tipo de vínculo
*   Factura en pantalla

<font color='0416ef'> **Cancelar reserva** </font>

El usuario puede cancelar una reserva activa ingresando documento y ID de la reserva.

**Resultados:**

*   El asiento vuelve a quedar libre
*   La reserva queda marcada como inactiva
*   Se actualiza la lista de reservas del usuario

<font color='0416ef'> **Menú administrativo** </font>
El administrador debe autenticarse con las siguientes credenciales:

*   Usuario: admin

*   Contraseña: udear123

**Funciones disponibles:**

*   Total de reservas registradas
*   Total de reservas activas
*   Total pagado
*   Promedio por venta
*   Usuario con más reservas
*   Usuario con menos reservas
*   Listado de usuarios con cantidad de reservas

<font color='0416ef'> **Exportación a CSV** </font>

El sistema genera automáticamente una carpeta export/ con:

**✔ usuarios.csv**

***Incluye:***

*   documento
*   nombre
*   apellido
*   tipo de vínculo
*   reservas_count

**✔ reservas.csv**

***Incluye:***

*   id reserva
*   documento usuario
*   id película
*   fila y columna
*   precio
*   fecha
*   estado (activa/cancelada)

<font color='0416ef'> **Problemas comunes** </font>

| Problema | Causa	| Solución |
|:---|:---|:---|
| No aparece el menú | No se ejecutó main()	| Ejecutar todas las celdas	|
| No permite reservar | Usuario no registrado	| Registrar usuario primero	|
| Asiento marcado como ocupado | Ya reservado	| Elegir otro asiento	|
| Reportes vacíos | No hay reservas	| Realizar al menos una reserva	|
|No se exportan archivos | Error en permisos	| Confirmar que la carpeta no esté protegida	|

<font color='0416ef'> **Vínculos académicos y descripción** </font>

**Información del proyecto**

Nombre: EL PROYECTOR DE LA UdeA

Curso: Algoritmia y Programación - 2025-2

Lenguaje: Python

Interacción: Consola

Persistencia: Archivos CSV

