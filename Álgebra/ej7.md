---
title: Ejercicios 7
author: David Charte
geometry: "a4paper, top=2.5cm, bottom=2.5cm, left=3cm, right=3cm"
fontsize: 10pt
header-includes:
  - \usepackage{tikz}
  - \usepackage{amsmath}
  - \providecommand{\abs}[1]{\left\lvert#1\right\rvert}
---

## Ejercicio 7.1

Sea $q$ una potencia de un entero primo positivo.

1. Demostrar que un polinomio irreducible de grado $r$ sobre $\mathbb F_q$ es un factor de $X^{q^n}-X$ si, y solo si, $r\mid n$.
1. Deducir que $X^{q^n}-X=\prod_i f_i(X)$, donde $f_i$ varía sobre todos los polinomios irreducibles cuyo grado divide a $n$.
1. Demostrar que si $t_r$ es el número de tales polinomios, entonces $\sum r t_r=q^n$, y deducir una fórmula para $t_r$, en términos de $q$, $r$ y la función de Möbius.


### Resolución

#### 1
$\underline\Leftarrow\ $ Si $\alpha$ es raíz, $\mathbb F_q(\alpha)/\mathbb F_q$ tiene grado $r$, y por tanto $\lvert \mathbb F_q(\alpha)\rvert=q^r$. Además, $x^{q^r}=x\ \forall x\in \mathbb F_q(\alpha)$. Puesto que $r\mid n\Rightarrow n = rm\Rightarrow x^{q^n}=x^{(q^r)^m}=x\ \forall x\in \mathbb F_q(\alpha)$. En particular, $\alpha$ es raíz de $X^{q^n}-X$.

$\underline\Rightarrow\ $ El polinomio descompone en un cuerpo $F$ contenido dentro de $\mathbb F_q^n$, teniendo la cadena de extensiones $\mathbb F_q^n/F$, $F/\mathbb F_q$ de forma que $F/\mathbb F_q$ es de grado $r$ y $\mathbb F_q^n/\mathbb F_q$ es de grado $n$, luego $r\mid n$.

#### 2

Tomamos la factorización en irreducibles del polinomio:
$$ X^{q^n}-X=\prod_j p_j(X) $$
Por el apartado 1, para cada $p_j$ factor irreducible se tiene que su grado divide a $n$, es decir, $\mbox{grad}(p_j)\mid n\ \forall j$. Además, cualquier $f_i$ es un irreducible cuyo grado divide a $n$ por lo que es uno de los factores $p_j$. Tenemos, por tanto, que cada $p_j$ se corresponde con uno y solo uno de los $f_i$.

#### 3

Podemos ver el grado como la suma de los grados de los irreducibles del apartado 2, en cuyo caso por cada grado $r\mid n$ tenemos $t_r$ polinomios, sumando $rt_r$. En total, $$q^n=\mbox{grad}\left(X^{q^n}-X\right)=\sum_{r\mid n} r t_r~.$$

Para dar una expresión en términos de $q$, $r$ y la función de Möbius vamos a utilizar la fórmula de inversión de Möbius[^mobiusinv]. Esta fórmula toma dos funciones aritméticas, $f(n)$ y $g(n)$, y afirma que si se verifica la siguiente igualdad:
$$g(n)=\sum_{r\mid n} f(r)$$
entonces se cumple lo siguiente:
$$f(n)=\sum_{r\mid n} \mu(r)g\left(\frac n r\right)\mbox{, donde }\mu\mbox{ es la función de Möbius.}$$

En este caso, la fórmula de inversión de Möbius nos dice que se tiene:
$$rt_r=\sum_{d\mid r}\mu(d)q^{\frac r d}\ \Rightarrow\ t_r=\frac 1 r\sum_{d\mid r}\mu(d)q^{\frac r d}~.$$

[^mobiusinv]:  Weisstein, Eric W. "Möbius Inversion Formula." <http://mathworld.wolfram.com/MoebiusInversionFormula.html>
