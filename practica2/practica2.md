#Práctica 2

##Resolución de la práctica paso a paso.

Primero, pasamos de una máquina a otra un fichero comprimido mediante ssh y comprimido mediante la orden tar. 
Para ello, antes de ejecutar la orden que se especifica en las prácticas, he creado un directorio llamado prueba, que será el directorio que comprima para enviar a la otra máquina. 
Se hace de la siguiente manera:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica2/ejecucionordensshM1.png)

Compruebo que se ha copiado bien en la máquina 2 después de utilizar el comando anterior de la siguiente manera:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica2/comprobacionfuncionamientosshM2.png)

Ahora, procedo a copiar el directorio /var/www/ de la máquina 1 en la máquina 2, y para ello utilizo el comando que se especifica en la práctica de la siguiente manera:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica2/ejecucionrsyncm2.png)

Compruebo que se ha copiado bien el directorio en la máquina 2 con el comando ls tal y como se especifica en la práctica también:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica2/comprobacioncopiarsyncenM2.png)

Ahora, para poder acceder a SSH sin contraseña, generamos las claves dsa en la Máquina 2 para poder acceder a la Máquina 1 sin contraseña. Las generamos de la siguiente manera: 

![imagen](https://github.com/Googlo/SWAP/blob/master/practica2/creaciondsa.png)

Una vez creadas, las copiamos a la Máquina 1 para que reconozca esta máquina mediante el archivo authorized_keys. Una vez hecho esto podremos acceder al root de la Máquina 1 sin necesidad de introducir contraseña. La ejecución de esto está en la siguiente imagen:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica2/copiadsaaM1ycomprobacionfuncionamiento.png)

Para la última tarea, para que se ejecute cada hora la copia del directorio /var/www/ configuro el archivo /etc/crontab/ de la siguiente manera:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica2/configuracioncrontab.png)

Lo he hecho así para que el primer 00 se haga a todas las horas en punto, ya que tengo puesto con los "*" que se haga a todas las horas, todos los días, todos los días del mes, todos los días de la semana, todos los meses, y mediante el usuario root. Y la misma orden que he usado antes con el rsync, solo que le añado --delete para que lo que se borre también se refleje en la máquina 2.