#Práctica 3

##Resolución de la práctica.

Instalando Nginx he tenido problemas con la versión 15.04 de Ubuntu Server, por lo que he tenido que hacer el balanceador con una máquina que contuviera como SO Ubuntu Server 12.04. Al poner este nuevo SO no he tenido ningún problema al instalar.

Una vez instalado Nginx, reinicio el servicio para comprobar que no hay ningún error y uso el comando "curl" para comprobar que puede ver el balanceador a las otras 2 máquinas, como está representado en la siguiente imagen:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica3/imgpra31.png)

Suponemos que es más potente la máquina 2, por lo que le asigno un peso de 2 y a la máquina 1 un peso de 1. En la siguiente imagen podemos ver cómo queda la configuración del balanceador:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica3/imgpra32.png)

Ahora, comprobamos que está funcionando bien el balanceador y está balanceando como hemos dicho según los pesos. He cambiado también el index.html de las dos máquinas para que se pueda ver cuándo está sirviendo la petición una máquina y cuando la está sirviendo la otra. Como se puede ver en la siguiente imagen, alterna 2 peticiones a la máquina 2 y 1 petición a la máquina 1, de forma que está haciendo caso a lo que hemos interpuesto con las direcctrices "weight".

![imagen](https://github.com/Googlo/SWAP/blob/master/practica3/imgpra33.png)

Procedo ahora a instalar Haproxy, y lo llevo a cabo sin ningún problema. No sin antes parar la ejecución de nginx, para que no haya problemas entre ellos, ya que escuchan desde el mismo puerto (el 80). 

Después, la configuración del Haproxy queda así:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica3/imgpra34.png)

Ejecutamos haproxy y comprobamos que está alternando las dos máquinas cuando se hacen peticiones a la dirección IP del balanceador:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica3/imgpra35.png)

