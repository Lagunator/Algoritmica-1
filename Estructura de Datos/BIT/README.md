<div align="center">

# BIT (Binary Indexed Tree)

 <div align="left">
 
 ### Definición  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Un BIT, también conocido como Fenwick Tree, es una estructura de datos que almacena los resultados de un operación -u operaciones- determinada en un intérvalo [0..j]. Esto con el propósito de solamente tener que obtener el resultado de la operación inversa entre los intérvalos [0..i] y [0..j] para poder obtener el resultado de la operación para el intérvalo [i..j].  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Aunque le llamemos Tree, en realidad el árbol como tal no existe. Todos los datos en realidad están guardados en un arreglo. Además, a diferencia de la estructura Segment Tree, no guardamos todos los valores del conjunto dado. Priorizamos el almacenamiento de la operación realizada en intérvalos de tamaños mayores a 1.  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Para poder construir un BIT, Binary Indexed Tree, debemos primero entender la operacion binaria Complemento 1 y también el concepto de bit menos significativo. El complemento 1 de un número binario es aquel que convierte los 1's del original en 0's y los 0's en 1's. Entonces si tenemos 11, su complemento 1 será 00. De esta operación derivará una segunda operación '-n(a <sub> 2 </sub>)', donde -n = complemento1(a <sub> 2 </sub>)	 + 1. Y el bit menos significativo de un número binario será el último número 1 presente en el número seguido de los ceros correspondientes. Si tenemos 1010, el bit menos significativo será 10; si tenemos 11100, será 100; si tenemos 1001, será 1; etc.  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Encontrar el bit menos significativo por medio de código es esencial. La nueva operación -n() nos ayudará. La manera en que encontraremos el bit menos significativo de un número binario será aplicando la operación 'and' al número binario a <sub> 2 </sub> y al resultado de -n(a <sub> 2 </sub>). Es decir, bms(a <sub> 2 </sub>) = a <sub> 2 </sub> AND -n(a <sub> 2 </sub>).  
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Teniendo bms(a <sub> 2 </sub>) ahora lo utilizaremos para determinar el intérvalo cuyo resultado se guardará en una posición a. El intérvalo para un nodo a será [padre(a)..a] de tal manera que padre(a) sea el resultado de restar bms(a <sub> 2 </sub>) a 'a <sub> 2 </sub>'. Entonces: padre(a) =  a <sub> 2 </sub> - bms(a <sub> 2 </sub>). Algo a denotar es que los nodos padres siempre serán potencias de a, es decir, [1,2,4,8,16..]. Sin embargo, aunque el guardado de datos de esta manera sea de hijo a padre, una vez que se implementa en código es de padre a hijo, de tal manera que primero almacenemos el valor correspondiente al padre en todos sus hijos y, luego, añadiremos el valor de los nodos hijos aplicando la operación al valor ya añadido y al del nodo hijo que está siendo introducido.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Cabe remarcar que esta estructura de datos se utiliza con grupos. Decimos que un conjunto de números es un grupo si es que es un monoide y además tiene un elemento inverso. Entonces, un conjunto S que es un grupo cumple con las siguientes características:   
    Para que sea un monoide:  
* Para todo par de números (a,b) que pertenecen a S, el resultado de la operación 'o' entre ellos debe también pertenecer a S. Es decir, aob=c y 'c' pertenece a S. Esta es el la propiedad de operación interna.  
* Para toda operación 'o' que se realice con los números (a,b,c) que pertenecen a S, el orden de realización no debe afectar el resultado. Es decir, ao(boc) = (aob)oc. Esta es la propiedad asociativa.  
* Un elemento 'e' debe pertenecer a S tal que la operación entre este elemento y cualquier otro número 'a' del conjunto, nos devuelva el elemento 'a'. Es decir, aoe=a. Esta es la propiedad neutra.  
    Para que sea un grupo:  
* Cada elemento 'a' del conjunto debe tener un inverso 'I' tal que la operación o entre estos dos elementos nos devuelva el elemento neutro 'e'. Es decir, aoI=e y Ioa=e. Esta es la propiedad inversa.  
 
 #### Ejemplo  

   ### Código  
  * []()  
  
  ### Problemas  
  * Palabra Compuesta  
  * Sopa de Letras  
  ### Modificaciones   
  * Suffix Trie  
  
  ## Bibliografía  
  * Algorithms for Competitive Programming Staff. (2022). [Fenwick Tree](https://cp-algorithms.com/data_structures/fenwick.html). Competitive Programming Algorithms.  
  * Geeks for Geeks Staff. (2022). [1’s and 2’s complement of a Binary Number](https://www.geeksforgeeks.org/1s-2s-complement-binary-number/). Geeks for Geeks.  
  * Tutorials Point Staff. (s. f.). [Discrete Mathematics - Group Theory](https://www.tutorialspoint.com/discrete_mathematics/discrete_mathematics_group_theory.htm#:~:text=A%20monoid%20is%20a%20semigroup,Closure%2C%20Associative%2C%20Identity%20element.). Tutorials Point.  
