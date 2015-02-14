Enunciado {#enunciado .unnumbered}
=========

Los números de Fibbonacci tienen la siguiente forma:

$F_1 = 1$\
$F_2 = 1$\
$F_3 = 2$\
$\vdots$\
$F_n = F_{n-2} + F_{n-1}$

Tenemos un array $a_1,a_2,\dots,a_N$ que contiene $N$ elementos.\
Y queremos encontrar $\gcd(F_{a_1},F_{a_2},\dots,F_{a_N})$.

El formato de entrada es:

-   La primera línea contiene el tamaño del array, $N$.

-   En las siguientes $N$ líneas hay un número, la i-ésima línea
    contiene $a_i$.

El formato de salida debe ser imprimir una sólo número entero, el resto
de la división entera del número resultado por $10^9+7$.

Las restricciones son:

-   $1 \leq N \leq 2 \times 10^5$

-   $1 \leq a_i \leq 10^{12}$

Solución {#solución .unnumbered}
========

Sean $n, k \in \mathbb{N}$. Se tiene que
$F_{n+k} = F_{k-1}F_n + F_k F_{n+1}$.

La prueba se realiza por inducción sobre $k$ para un $n$ arbitrario en
cada paso. Para $k=1$ es trivial denotando $F_0 = 0$. Supongamos el
resultado cierto para $k \in \mathbb{N}$.
$$F_{n+k+1} = F_{k-1}F_{n+1} + F_k F_{n+2} = F_{k-1}F_{n+1} + F_k (F_{n} + F_{n+1}) = F_{k}F_n + F_{k+1} F_{n+1}$$
donde se ha utilizado en primer lugar la hipótesis de inducción para $k$
y posteriormente la definición de la sucesión dos veces.

Sean $n, k \in \mathbb{N}$. Se tiene que
$\gcd(F_n, F_{k+n}) = gcd(F_n, F_k)$.

En primer lugar:
$$\gcd(F_n, F_{n+1}) = \gcd(F_{n}, F_{n}+F_{n-1}) = \gcd(F_{n}, F_{n-1})$$
donde se ha utilizado que $\gcd(a,b) = \gcd(a,b-qb)$ para cualquier $q$.
Por inducción se llega a que
$$\gcd(F_n, F_{n+1}) = \gcd(F_{1}, F_{2}) = \gcd(1,1) = 1$$ Luego los
términos consecutivos de la sucesión de Fibonacci son primos relativos
entre sí.

Ahora, para $k > 1$ usamos la proposición anterior:
$$\gcd(F_n, F_{n+k}) = \gcd(F_n, F_{k-1}F_n + F_k F_{n+1}) = \gcd(F_n, F_k F_{n+1})$$
Como $F_n$ y $F_{n+1}$ son primos relativos:
$$\gcd(F_n, F_{n+k}) = \gcd(F_n, F_k F_{n+1}) = \gcd(F_n, F_k)$$

Sean $a, b \in \mathbb{N}$. Se tiene que
$\gcd(F_a, F_b) = F_{gcd(a, b)}$.

Si $a=b$ es trivial. Supongamos que $a < b$ sin pérdida de generalidad.
Tenemos que $\gcd(F_a, F_b) = gcd(F_a, F_{b-a})$. Podemos repetir el
proceso hasta que aparezca un 0 en los índices. Estamos haciendo en
definitiva el Algoritmo de Euclides sobre los índices y por ser el mismo
proceso tenemos garantizado que el índice final no nulo es el máximo
común divisor. Esto es:
$$\gcd(F_a, F_b) = \gcd(F_0, F_{\gcd(a,b)}) = \gcd(0, F_{\gcd(a,b)}) = F_{\gcd(a,b)}$$

Sean $n \in \mathbb{N}$ y $a_1, \dots a_n \in \mathbb{N}$. Se tiene que
$\gcd(F_{a_1}, \dots, F_{a_n}) = F_{gcd(a_1, \dots, a_n)}$.

Usaremos que
$\gcd(b_1, \dots, b_n) = \gcd( \gcd(b_1, b_2), b_3, \dots, b_n)$:
$$\gcd(F_{a_1}, \dots, F_{a_n}) = \gcd(\gcd(F_{a_1},F_{a_2}), F_{a_3}, \dots, F_{a_n}) = \gcd(F_{\gcd(a_1, a_2)}, F_{a_3}, \dots, F_{a_n})$$
Repetimos el proceso $n-1$ veces y usando la definición del máximo común
divisor de $n$ elementos obtenemos el resultado.

Dados $a_1, \dots, a_n \in \{1, \dots, 10^{12}\}$ con
$n \in \{1, \dots, 2 10^5\}$. Realizamos el siguiente algoritmo:

1.  Calculamos $m = \gcd(a_1, \dots, a_n)$.

2.  Calculamos $F_m \mod 10^9+7$

Para calcular el máximo común divisor de la lista utilizamos el
Algoritmo de Euclides para los dos primeros elementos de la lista que
quedan sustituidos por el resultado obtenido. Repetimos el proceso hasta
obtener un único número final que es el máximo común divisor buscado.
Este algoritmo tiene eficiencia $n$ por la del propio Algoritmo de
Euclides

Para calcular $F_m \mod 10^9+7$ tenemos que tener en cuenta que $m$
puede ser hasta $10^{12}$. Es fácil realizar un algoritmo lineal para
este propósito calculando todos los términos progresivamente y guardando
solo los dos últimos en cada iteración.

