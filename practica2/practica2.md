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