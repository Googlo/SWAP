#Práctica 4

##Resolución de la práctica.

He instalado una cuarta máquina que pueda ver al resto de máquinas para la realización de la práctica, y poder lanzar los benchmarks desde ella.

He preparado también un archivo html que es al que le vamos a hacer las peticiones, que es como sigue en la siguiente captura:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica4/imgpra41.png)

La primera prueba la estamos haciendo mandando peticiones a la granja web con Haproxy funcionando.

Tras realizar la orden "ab -n 1000 -c 5 http://192.168.1.102/hola.html" obtenemos los siguientes resultados la primera vez:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica4/imgpra42.png)

Tras 5 ejecuciones, obtenemos los siguientes resultados:

|GW         | Time taken per tests (s) | Failed requests | Requests per second |
|:---------:|:------------------------:|:---------------:|:-------------------:|
|1          |0,776                     |0                |1288	               | 
|2          |0,818                     |0                |1222	               |
|3          |0,833                     |0                |1200	               |
|4          |0,809                     |0                |1236	               |
|5          |0,800                     |0                |1249	               |
|**Media**  |**0,8072**                |**0**            |**1239,0**           |

Ahora vamos a realizar la misma prueba que antes, pero en vez de con Haproxy haciendo de balanceador, vamos a usar Nginx:

Estos son los resultados obtenidos la primera ejecución:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica4/imgpra43.png)

Tras 5 ejecuciones, estos son los datos:

|GW         | Time taken per tests (s) | Failed requests | Requests per second |
|:---------:|:------------------------:|:---------------:|:-------------------:|
|1          |1,047                     |0                |0955	               | 
|2          |1,045                     |0                |0957	               |
|3          |0,925                     |0                |1081	               |
|4          |1,097                     |0                |911	               |
|5          |0,994                     |0                |1005	               |
|**Media**  |**1,0216**                |**0**            |**981,81**           |

Ahora vamos a realizar la misma prueba que antes, pero mandando las peticiones directamente a la máquina 1.

Aquí tenemos un ejemplo de la primera ejecución que hemos realizado contra la máquina 1:

![imagen](https://github.com/Googlo/SWAP/blob/master/practica4/imgpra44.png)

Estos son los resultados tras 5 ejecuciones:

|M1         | Time taken per tests (s) | Failed requests | Requests per second |
|:---------:|:------------------------:|:---------------:|:-------------------:|
|1          |0,556                     |0                |1797	               | 
|2          |0,545                     |0                |1833	               |
|3          |0,528                     |0                |1895	               |
|4          |0,533                     |0                |1876	               |
|5          |0,551                     |0                |1814	               |
|**Media**  |**0,5426**                |**0**            |**1843,0**           |


Se puede ver cómo los tiempos se reducen sin usar el balanceador de carga, ya que las peticiones van directamente al servidor. Era de esperar desde un principio que obtuviéramos resultados similares a estos.

