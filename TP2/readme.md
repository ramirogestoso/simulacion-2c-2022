# Trabajo Practico 2

**Consideraciones generales**

El trabajo debe realizarse en una Notebook de Python. En cada ejercicio deben estar explicados/justificados todos los pasos y procedimientos realizados (de forma detallada) para llegar a la resolución del mismo.

La entrega debe efectuarse por Campus, no siendo necesario que todos los miembros del grupo la realicen. La misma debe incluir el código/desarrollo utilizado para resolver el trabajo práctico y las diapositivas utilizadas en la presentación.

## Ejercicio 1

A partir del universo de página webs provistas junto al enunciado, se pide:

- Calcular el pagerank para cada sitio. (Mostrar la matriz generada)
- Simular 20 búsquedas de palabras elegidas al azar dentro de las existentes en los textos de las páginas, y mostrar las mismas en función de la importancia asignada a cada sitio.

## Ejercicio 2

En base a lo presentado en el trabajo “Queuing theory application in imaging service analysis for small Earth observation satellites”, simular los resultados obtenidos sobre la longitud de imágenes en cola esperando ser procesadas en la sección 3.1. Pure image capture service system.

El ejercicio se puede resolver utilizando simpy o programación tradicional (a elección del grupo).

## Ejercicio 3

Se está diseñando un web service, el cual cada vez que es invocado consulta a una base de datos.

Se estima que el tiempo que transcurre entre cada llamada al servicio se puede modelar según una distribución exponencial con media $ \{textmu} = 4 segundos $ 

Se debe decidir la arquitectura de base de datos a utilizar entre las dos siguientes:

1. Utilizar 2 bases de datos distribuidas.

    Con probabilidad las solicitudes son atendidas por la base 1 y con probabilidad son atendidos por la base de datos 2.
    El tiempo que demora cada base de datos en atender una solicitud sigue una distribución exponencial con medias, y respectivamente.

2. Utilizar 1 base de datos central.

    En este caso la demora en resolver una solicitud sigue una distribución exponencial con $ \{textmu} = 0.8 segundos $

    Simular para cada opción 100.000 solicitudes procesadas, determinando:
    
    - El tiempo medio de espera entre que la solicitud llega y puede ser procesada (suponer que ninguna conexión cae por timeout).
    - La fracción de las solicitudes que no esperaron para ser procesadas.
    - Probar con distintos escenarios, modificando los parámetros del ejercicio.

    El ejercicio se puede resolver utilizando Simpy o programación tradicional (a elección del grupo)

## Ejercicio 4

Una entidad financiera está analizando cambiar uno de sus cajeros automáticos por uno con la funcionalidad de reciclador de billetes (si un cliente realiza un depósito de efectivo, ese efectivo estará disponible para que lo pueda retirar otro cliente).

El cajero automático actual, que se quiere reemplazar, es de tipo estándar. No recicla los billetes, sino que posee dos compartimentos, uno con dinero para entregar y otro donde guarda el dinero que se deposita.

Esto presenta los siguientes problemas:
- Si no tiene más efectivo para entregar en el compartimento de retiro de dinero, no entrega efectivo
aunque tenga en el compartimento de depósitos.
- Si el compartimento que recibe los depósitos se completa, no puede recibir más.

La entidad conoce que con el cajero actual el 20% de los clientes se retiraba sin poder extraer dinero, y sólo acepta cambiarlo si este porcentaje disminuye.

Por simplicidad suponer que el cajero sólo expende billetes de $100, tiene una capacidad máxima de 2000 billetes, y comienza el día con su carga completa.

Si un cliente quiere extraer dinero y el cajero no cuenta con la suma suficiente, se va del mismo sin retirar nada.

Algo similar ocurre cuando un cliente desea depositar efectivo y la capacidad máxima de billetes en el cajero fue alcanzada, retirándose sin poder depositar.

En el relevamiento que realizó la entidad diferenció a sus clientes en dos grupos:

    Grupo 1: Sólo retiran efectivo, y corresponden al 75% de los clientes que arriban. El tiempo que utilizan el cajero se puede modelar con una distribución exponencial de media 90 segundos.
    Cada cliente de este grupo, extrae una cantidad de billetes que sigue una distribución uniforme [3,50].
    
    Grupo 2: Sólo realizan depósitos, son el 25% de los clientes totales.
    Utilizando el cajero un tiempo que siguen una distribución exponencial de media 5 minutos.
    Cada cliente de este grupo, deposita una cantidad de billetes que se puede modelar utilizando una distribución uniforme [10,110].

La frecuencia de arribos de clientes es de 1 cliente cada 10 minutos con distribución exponencial.

Se pide:

a. Simular 1000 días completos de 24 hrs.
b. Para un día en particular graficar la cantidad de billetes en el cajero luego de cada transacción.
c. Calcular el tiempo medio que los clientes demoraron en el sistema (espera + utilización del cajero)
d. ¿Recomienda a la entidad que implemente el cambio de cajero?

El ejercicio se puede resolver utilizando Simpy o programación tradicional (a elección del grupo)