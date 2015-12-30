---
title: Ejercicios - Espacio topológico
author: Diego Asterio de Zaballa
source: Topología, Rafael Lopez Camino
geometry: "a4paper, top=2.5cm, bottom=2.5cm, left=3cm, right=3cm"
fontsize: 10pt
header-includes:
  \usepackage{tikz}
---

### Ejercicio 1.1

Sea $X$ un conjunto y $\{ \tau_i : \in I \}$ una familia de topologías definida en $X$. Probar que $\bigcap_{ i \in I}\tau_i$ es una topología en $X$. Dar un ejemplo de la unión de dos topologías en un conjunto no tiene porqué ser una 
topología.

#### Solución

## a)
  
  Para verificar que el conjunto $\bigcap_{ i \in I} \tau_i$ es una topología en $X$ este debe verificar tres propiedades:
  
  1. $X,\emptyset \in \bigcap_{ i \in I} \tau_i$
  2. $\bigcup_{ \alpha \in \Lambda} O_\alpha \in \bigcap_{ i \in I} \tau_i$  $\forall \{O_\alpha\} \subset \bigcap_{ i \in I} \tau_i$
  3. $O_1 \cap O_2 \in \bigcap_{ i \in I} \tau_i$  $\forall O_1,O_2 \in \bigcap_{ i \in I} \tau_i$
  
  Para empezar, $X,\emptyset \in \tau_i \forall i \in I$ de esa manera $X,\emptyset \in \bigcap_{ i \in I} \tau_i$
  
  Para la segunda propiedad razonamos como sigue. Sea $O \in \bigcap_{ i \in I} \tau_i$ entonces nuestro abierto $O \in \tau_i \forall i \in I$.
  Tomemos ahora una familia de conjuntos $\{O_\alpha\}$ tal que $\forall \alpha \in \Lambda O_\alpha \in \tau_i$ para todos los indices de $\tau_i$
  entonces la union arbitraría de $O_\alpha$ pertenecería a cada una de las $\tau_i \forall i \in I$. De esto podemos concluir que $\bigcup_{\alpha 
  \in \Lambda} O_\alpha \in \bigcap_{ i \in I} \tau_i$
  
  Por último tomando $O_1,O_2 \in \bigcap_{ i \in I} \tau_i$ tanto $O_1$ como $O_2$ pertenecen a $\tau_i \forall i \in I$ asi que su intersección también
  pertenecerá a $\tau_i \forall i in I$ y entonces se puede concluir que $O_1 \cap O_2 \in \bigcap_{ i \in I} \tau_i$.
  
## b)
  
  Para dar un ejemplo en el que la unión de dos topologías no es una topología nos situamos en $\mathbb{R}$ con dos 
  topologías $\tau_i = \tau ( \beta_i )$ la topología generada por la base $\beta_i = \{  ]\infty,a]: a \in \mathbb{R} \}$ también conocida como la topologia a izquierdas y la topologia a derechas $\tau_d = \tau ( \beta_d )$
  generada por la base $\beta_d = \{  [ b\infty [: b \in \mathbb{R} \}$ . En ella se ve claramente que $\tau = \tau_i \cup \tau_d$
  no es una topología. Tomamos $O_1 = [a,\infty[$ y $O_2 = ]\infty,b]$ con a < b entonces $O_1 \cap O_2 = [a,b] \notin \tau$ y por tanto como la intersección finita de elementos del conjunto no permanece en el conjunto $\tau$ no es una topología.

### Ejercicio 1.2

  Hallar todas las topologías que se pueden definir en un conjunto con tres elementos.
  
#### Solución
  
  Tomando un conjunto $X$ de tres elementos $X = \{a,b,c\}$ estas son las topologías que se pueden definir en el:
  
  1. La topología trivial
  2. La topología discreta
  3. $\tau = \{\{a\},X,\emptyset\}$
  4. $\tau = \{\{a\},\{b\},\{a,b\},X,\emptyset\}$

  (Como los elementos a,b y c son elementos cualesquiera las topologías tres y cuatro son equivalentes al resto de topologías que se puedan formar)
  
  
  
### Ejercicio 1.3

  Se considera un conjunto $X$ y $A,B \in X$. Se define $\tau = \{\emptyset,X,A,B\}$. Determinar qué propiedades deben tener $A$ y $B$ para que $\tau$ sea una topología en $X$.
  
#### Solución

  Para que $\tau$ sea una topología $A$ y $B$ deben cumplir que tanto la unión como la interseccion este contenida en la propia topología.

### Ejercicio 1.4 

  Sea $X = \{a,b,c,d\}$ y $A = \{a,b\}$. Hallar todas las topologías que se pueden definir en $X$ de forma que $A$ sea un 
  conjunto abierto y cerrado a la vez.
  
#### Solución

  Las topologías que se pueden definir en $X$ cumpliendo lo anterior son:
  
  1. La topologia discreta
  2. $\tau = \{\{a,b\},\{c,d\},X,\emptyset\}$
  3. $\tau = \{\{a\},\{b\},\{a,b\},\{c,d\},\{a,c,d\},\{b,c,d\},X,\emptyset\}$
  4. $\tau = \{\{c\},\{d\},\{a,b\},\{c,d\},\{a,b,c\},\{a,b,d\},X,\emptyset\}$
  
### Ejercicio 1.5

  Si $X = \{a,b,c,d\}$ es un conjunto, probar que $\tau = \{\emptyset,X,\{a\},\{a,b\}\}$ es una topología. Hallar el interior y la adherencia de los conjuntos $\{a,d\}$ y $\{b,c,d\}$.
 
#### Solución

  Tanto $\emptyset$ como $X$ pertenecen al conjunto $\tau$. El número de elementos es finito y podemos comprobar casi 
  de forma inmediata como la unión de cualquier familia de elementos de $\tau$ ($\{O_\alpha\} \alpha \in \Lambda$) pertenece
  a $\tau$. Además la intersección de dos elementos cualesquiera del conjunto $\tau$ se encuentra en el mismo conjunto.
  
  El interior de los conjuntos $\{a,d\}$ y $\{b,c,d\}$ es $Int(\{a,d\}) = \{a\}$ y $Int(\{b,c,d\}) = \emptyset$ y la adherencia es $\overline{\{a,d\}} = \{a,d\} \cup Fr(\{a,d\}) = \{a,d\} \cup \{b,c,d\} = X$ y $\overline{\{b,c,d\}} = \{b,c,d\} \cup Fr(\{b,c,d\}) = \{b,c,d\} \cup \{b,c,d\} = \{b,c,d\}$
  
### Ejercicio 1.6
  
  En $\mathbb{N}$ se define la siguiente familia $\tau$ de subconjuntos. Un conjunto $O \in \mathbb{N}$ pertenece a $\tau$ 
  si satisface la siguiente propiedad: "si $n\in O$, entonces todos los divisores de $n$ pertenecen a $O$". Probar que   
  $\tau$ define una topología en $\mathbb{N}$ llamada *topología de los divisores*. Hallar una base de entornos para cada 
  $n \in \mathbb{N}$ con el menor número posible de entornos. Hallar el interior y la adherencia de los conjuntos $A = {2n 
  : n \in \mathbb{N}}$ y $B = \{4,5\}$. 
  
#### Solución

  Cualquier número natural o es irreducible o se puede dividir por otro número natural por lo tanto $\mathbb{N} \in \tau$ y de forma trivial $\emptyset \in \tau$. Asi la primera propiedad para que $\tau$ sea una topología se cumple.

  En segundo lugar si tomamos una familia de conjuntos $\{O_\alpha\} \alpha \in \Lambda$ perteneciente a $\tau$ para todo $n \in \bigcup_{\alpha \in \Lambda}O_\alpha$ estan sus divisores por estar para algún $\alpha$. 

  Y por último sean $O_1, O_2 \in \tau$ para cualquier $n \in O_i i=1 \vee i=2$ por la propiedad que cumplen todos los abiertos estan todos sus divisores de modo que $\forall n \in O_1 \cap \O_2$ estan los divisores de $n$ por estar tanto en $O_1$ como en $O_2$. Asi se cumple que $O_1 \cap O_2$ pertenece al conjunto $\tau$.

  $A = \{2n : n \in \mathbb{N}\}$ sea $x$ un elemento de $A$ el conjunto $D_x = \{ divisores de x \}$ es el unico conjunto dentro de $\tau$ que cumple $D_x \in \mathcal{U}$  asi solo si $D_x \subset A$ podemos decir que $x$ es un punto interior de $A$ de modo que $int(A) = \{ 2p : p = 2^n\}$ para algún $n$. $\overline{A} = A \cup Fr(A)$ asi que para saber la adherencia sólo necesitamos saber la frontera del conjunto $A$.

