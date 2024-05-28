# Explicación del código

Este código crea un sistema donde múltiples trabajadores realizan tareas concurrentemente. Las tareas se envían a los trabajadores a través de un canal, y cada trabajador realiza las tareas que recibe.

Explicación del código:

- Se define una estructura Worker que tiene un campo id y un método PerformTask que realiza una tarea.
- Se define una estructura Task que tiene campos id y data.
- En la función principal (main), se crea un canal para recibir tareas, y crea múltiples trabajadores que escuchan este canal.
- Cada trabajador corre en su propia goroutine y realiza tareas a medida que las recibe del canal.
- Se crea múltiples tareas y las enviamos a los trabajadores a través del canal.
- Una vez que todas las tareas han sido enviadas, se cierra el canal para indicar que no se enviarán más tareas.
- Se utiliza un WaitGroup para esperar a que todos los trabajadores terminen antes de imprimir un mensaje final.

Este código demuestra varios conceptos de concurrencia en Go, incluyendo:

- Goroutines: Cada trabajador corre en su propia goroutine, lo que les permite realizar tareas concurrentemente.
- Channels: Se usa un canal para comunicarnos entre la goroutine principal y las goroutines de los trabajadores.
- WaitGroups: Se usa un WaitGroup para esperar a que todos los trabajadores terminen antes de continuar.
