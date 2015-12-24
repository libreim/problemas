---
title: Ejercicios Semana 6
author: David Charte
geometry: "a4paper, top=2.5cm, bottom=2.5cm, left=3cm, right=3cm"
fontsize: 10pt
header-includes:
  - \usepackage{tikz}
  - \usepackage{amsmath}
  - \providecommand{\abs}[1]{\left\lvert#1\right\rvert}
---
## Ejercicio 6.1

Se considera el grupo $C_p\times C_p$ siendo $p$ un entero primo positivo.

1. Prueba que $\mathrm{Aut}(C_p\times C_p)$ es el grupo lineal general $\text{GL}(p,2)$
1. Para $p=2$ prueba que $\mathrm{Aut}(C_2\times C_2)\cong S_3$
1. Determina el grupo $(C_2\times C_2)\rtimes C_2$
1. Para $p=3$ calcular el grupo $\mathrm{Aut}(C_3\times C_3)$ y su estructura
1. Determina un elemento de orden 3 de  $\mathrm{Aut}(C_3\times C_3)$
1. Determina el grupo $(C_3\times C_3)\rtimes C_3$

### Resolución

#### 1
Si tenemos $f:C_p\times C_p\longrightarrow C_p\times C_p$ automorfismo, tenemos que $C_p\cong \mathbb Z_p$ y sabemos que $\mathrm{End}_\mathbb Z(\mathbb Z_p\times \mathbb Z_p)\cong\mathrm{End}_{\mathbb Z_p}(\mathbb Z_p\times \mathbb Z_p)$. Entonces, puesto que $\{e_1=(1, 0), e_2=(0,1)\}$ es una base de $\mathbb Z_p\times \mathbb Z_p$, $f$ será de la forma

$$f(x) = f\binom{x_1}{x_2}=\begin{pmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{pmatrix}\binom{x_1}{x_2}\mbox{, donde }f(e_1)=\binom{a_{11}}{a_{21}}\mbox{ y }f(e_2)=\binom{a_{12}}{a_{22}},\ a_{ij}\in\mathbb Z_p~.$$

Por tanto tenemos que $\mathrm{Aut}(C_p\times C_p)\cong\text{GL}(p,2)$.

#### 2
Siguiendo la idea del apartado anterior, $\mathrm{Aut}(C_2\times C_2)\cong\text{GL}(2,2)$, y obtenemos 6 matrices regulares posibles:

$$
\text{GL}(2,2) = \left\{
\text{Id}=\begin{pmatrix}
1 & 0 \\ 0 & 1
\end{pmatrix},
\alpha=\begin{pmatrix}
1 & 1 \\ 0 & 1
\end{pmatrix},
\beta=\begin{pmatrix}
1 & 0 \\ 1 & 1
\end{pmatrix},
\gamma=\begin{pmatrix}
0 & 1 \\ 1 & 0
\end{pmatrix},
\delta\begin{pmatrix}
1 & 1 \\ 1 & 0
\end{pmatrix},
\delta^2=\begin{pmatrix}
0 & 1 \\ 1 & 1
\end{pmatrix}\right\},
$$

de las que la primera es la identidad, las tres siguientes de orden 2 y las dos últimas de orden 3. Por tanto, el grupo que nos dan es $S_3$.

#### 3
$(C_2\times C_2)\rtimes C_2$ está compuesto de 8 elementos:
$$
(C_2\times C_2)\rtimes C_2 = \{
((1,1),1),
((1,1),a),
((1,a),1),
((1,a),a),
((a,1),1),
((a,1),a),
((a,a),1),
((a,a),a)\}$$
con el siguiente producto:
$$
((a_1,b_1),c_1)((a_2,b_2),c_2)=((a_1,b_1)\phi(c_1)(a_2,b_2), c_1c_2)
$$
donde $\phi:C_2\rightarrow\mathrm{Aut}(C_2\times C_2)\cong \text{GL}(2,2)$ es un homomorfismo, luego $\phi(1)=\text{Id}$ y $\phi(a)$ es un elemento de orden 2, por tanto es $\alpha$, $\beta$ o $\gamma$. En cualquiera de los casos nos da un grupo no abeliano:
$$
((1,1),a)((1,a),1)=(\phi(a)(1,a),a)\neq((1,a),a)=((1,a),1)((1,1),a)$$

Luego sólo se puede tratar de $D_4$ o $Q$ (el grupo de los cuaternios). Puesto que hay más de un elemento de orden 2:
$$
((1,1),a)^2=((1,1),1);\ ((1,a),1)^2=((1,a)^2,1)=((1,1),1)$$
no puede ser el grupo de los cuaternios. Por tanto sea cual sea el valor de $\phi(a)$ se tiene que $(C_2\times C_2)\rtimes C_2\cong D_4$.

#### 4
Por el apartado 1, $\mathrm{Aut}(C_3\times C_3)\cong\text{GL}(3,2)$. Una matriz $2\times 2$ regular en $\mathbb Z_3$ es:
$$
\begin{pmatrix}a&b\\c&d\end{pmatrix}\mbox{ tal que }ad-bc\neq 0$$

Hay $3^4=81$ matrices $2\times 2$ posibles en $\mathbb Z_3$, pero no son regulares las que tienen dos filas o columnas proporcionales ($3^2\cdot 3 - 2 = 25$) ni las que tienen 3 ceros ($4\text{ posiciones}\cdot 2\text{ números} = 8$) $\Rightarrow\abs{\text{GL}(3,2)}=48=2^4\cdot 3$.

Los $2$-subgrupos de Sylow serán de orden 16 y los $3$-subgrupos de Sylow de orden 3. En concreto, $n_2\equiv 1\mbox{(mod 2)}\wedge n_2\mid 3\Rightarrow n_2\in\{1,3\}$, $n_3\equiv 1\mbox{(mod 3)}\wedge n_3\mid 16\Rightarrow n_3\in\{1,4,16\}$. Por tanto, tenemos las posibles soluciones $n_2 = 1\wedge n_3=16$ y $n_2 = 3\wedge n_3=1$. Veamos que la segunda posibilidad no puede ocurrir: si $n_3 = 1$ entonces sólo hay 2 elementos de orden 3 en $\text{GL}(2,2)$, pero vemos que podemos encontrar más elementos:
$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix}; A^2=\begin{pmatrix}1&2\\0&1\end{pmatrix}; A^3=\begin{pmatrix}1&0\\0&1\end{pmatrix}~.$$
$$B=\begin{pmatrix}1&0\\1&1\end{pmatrix}; B^2=\begin{pmatrix}1&0\\2&1\end{pmatrix}; B^3=\begin{pmatrix}1&0\\0&1\end{pmatrix}~.$$
$$C=\begin{pmatrix}1&2\\0&1\end{pmatrix}; C^2=\begin{pmatrix}1&1\\0&1\end{pmatrix}; C^3=\begin{pmatrix}1&0\\0&1\end{pmatrix}~.$$

Por tanto, debemos tener un $2$-subgrupo de Sylow y 16 $3$-subgrupos de Sylow.

#### 5
Para buscar un elemento de orden 3, simplemente buscamos el asociado a una matriz de $GL(3,2)$ que al elevarla a 3 dé la identidad:
$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix}; A^2=\begin{pmatrix}1&2\\0&1\end{pmatrix}; A^3=\begin{pmatrix}1&0\\0&1\end{pmatrix}~.$$

El elemento de $\mathrm{Aut}(C_3\times C_3)$ que buscamos es $\varphi:C_3\times C_3\rightarrow C_3\times C_3$ dada por $\varphi(1, 0)=(1, 0)$, $\varphi(0,1)=(1,1)$.

#### 6
$(C_3\times C_3)\rtimes C_3$ está compuesto de 27 elementos con el producto
$$
((a_1,a_2),b_1)((a_3,a_4),b_2)=((a_1,a_2)\phi(b_1)(a_3,a_4),b_1b_2)$$

donde $\phi:C_3\rightarrow\mathrm{Aut}(C_3\times C_3)$ es un homomorfismo con $\phi(1)=\mathrm{Id}$, $\phi(a)$ un elemento de orden 3 y $\phi(a^2)=\phi(a)^2$. Al igual que en el apartado 3, el grupo es no abeliano. Existen resultados que nos dicen que únicamente existen dos grupos no abelianos de orden $p^3$ (con $p$ primo)[^conrad]. En particular,
$$(C_3\times C_3)\rtimes C_3\cong\left\{\begin{pmatrix}a&b\\0&1\end{pmatrix}:a,b\in \mathbb Z_9, a\equiv 1\mbox{ (mod 3)}\right\}~.$$

[^conrad]: [Groups of order $p^3$ - Keith Conrad](http://www.math.uconn.edu/~kconrad/blurbs/grouptheory/groupsp3.pdf)
