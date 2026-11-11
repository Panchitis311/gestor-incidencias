1. ¿Por qué el frontend no necesita conectarse a PostgreSQL?
Porque la API ya se comunica tanto con el frontend como con la base de datos, es la que los une.
2. ¿Por qué el backend pertenece a dos redes?
Porque en una se comunica con el frontend, y en otra con la base de datos.
3. ¿Qué servicio necesita publicar un puerto en el anfitrión?
El frontend para que se pueda visualizar la aplicación.
4. ¿Por qué publicar PostgreSQL hacia fuera no es la solución adecuada para un fallo de comunicación interno?
Porque si publicara PostgreSQL hacia fuera, alguien con acceso a mi red, podría conectarse, con los problemas que eso conlleva, además que en un fallo de comunicación interno, la causa estaría en las redes o en el nombre de servicio, por lo que mostrar PostgreSQL no soluciona nada.
5. ¿Qué ventaja ofrece Docker Compose respecto a ejecutar los tres contenedores manualmente?
Que con un solo comando, podemos levantar y reiniciar todo.
6. ¿Por qué hemos dividido la arquitectura en dos redes?
Para poder aislar la base de datos y que no esté publicada en la red, por posibles problemas.
7. ¿Por qué el backend utiliza `db` como dirección de PostgreSQL?
Porque al levantar los contenedores, las IP cambian, por lo que se pone con el nombre del servicio.
8. ¿Qué diferencia existe entre detener un proyecto y eliminar sus volúmenes?
Si detienes el proyecto, la información almacenada se guarda en el volumen, y si vuelves a levantar el proyecto, te aparece la información guardada, en cambio si eliminas el volumen pierdes toda la información.
9. ¿Qué consecuencias tendría para la empresa perder el volumen de PostgreSQL?
Perder toda la información contenida en ese volumen.