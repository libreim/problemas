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

Sea $X$ un conjunto y $\{ \tau_i : \in I \}$ una familia de topologías definida en $X$. Probar que $\bigcap_{ i \in I}
\tau_i$ es una topología en $X$. Dar un ejemplo de la unión de dos topologías en un conjunto no tiene porqué ser una 
topología.

## a)
  
  Para verificar que el conjunto $  \bigcap_{ i \in I} \tau_i $ es una topología en $X$ este debe verificar tres propiedades:
  
  1. $ X,\emptyset \in \bigcap_{ i \in I} \tau_i $
  2. $ \bigcup_{ \alpha \in \Alpha} O_\alpha \in \bigcap_{ i \in I} \tau_i$  $\forall \{O_\alpha\} \subset \bigcap_{ i \in I} \tau_i $
  3. $ O_1\capO_2 \in \bigcap_{ i \in I} \tau_i $  $ \forall O_1,O_2 \in \bigcap_{ i \in I} \tau_i $
  
  Para empezar, $ X,\emptyset \in \tau_i \forall i \in I $ de esa manera $ X,\emptyset \in \bigcap_{ i \in I} \tau_i $
  
  Para la segunda propiedad razonamos como sigue. Sea $ O \in \bigcap_{ i \in I} \tau_i $ entonces nuestro abierto $ O \in \tau_i \forall i \in I $.
  Tomemos ahora una familia de conjuntos $\{O_\alpha\}$ tal que $ \forall \alpha \in \Lambda O_\alpha \in \tau_i $ para todos los indices de $\tau_i$
  entonces la union arbitraría de $O_\alpha$ pertenecería a cada una de las $\tau_i \forall i \in I$. De esto podemos concluir que $\bigcup_{\alpha 
  \in \Lambda} O_\alpha \in \bigcap_{ i \in I} \tau_i$
  
  Por último tomando $ O_1,O_2 \in \bigcap_{ i \in I} \tau_i$ tanto $\O_1$ como $O_2$ pertenecen a $\tau_i \forall i \in I$ asi que su intersección también
  pertenecerá a $\tau_i \forall \i in \I$ y entonces se puede concluir que $O_1\capO_2 \in \bigcap_{ i \in I} \tau_i$.
  
## b)
  
  Para dar un ejemplo en el que la unión de dos topologías no es una topología nos situamos en $ \mathbb{R} $ con dos 
  topologías $ \tau_i = \tau ( \beta_i ) $ la topología generada por la base $ \beta_i = \{  ]\infty,a]: a \in 
  \mathbb{R} \}$ también conocida como la topologia a izquierdas y la topologia a derechas $ \tau_d = \tau ( \beta_d ) $
  generada por la base $ \beta_d = \{  [ b\infty [: b \in \mathbb{R} \} $ . En ella se ve claramente que $ \tau = \tau_i \cup \tau_d $
  no es una topología. Tomamos $ O_1 = [a,\infty[ $ y $ O_2 = ]\infty,b] $ con a < b entonces $ O_1\capO_2=[a,b] \nin \tau $ 
  y por tanto como la intersección finita de elementos del conjunto no permanece en el conjunto $\tau$ no es una topología.

### Ejercicio 1.2

  
