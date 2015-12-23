---
title: Ejercicios Semana 4
author: David Charte
geometry: "a4paper, top=2.5cm, bottom=2.5cm, left=3cm, right=3cm"
fontsize: 10pt
header-includes:
  - \usepackage{tikz}
  - \usepackage{amsmath}
  - \providecommand{\abs}[1]{\left\lvert#1\right\rvert}
---

## Ejercicio 4.1

Sea $E/K$ una extensión algebraica tal que para cualquier extensión finita $F/K$ existe un $K$-homomorfismo $\sigma:F/K\longrightarrow E/K$. Demuestra que entonces $E$ es una clausura algebraica de $K$.

### Resolución

Para que $E$ sea una clausura algebraica necesitamos que sea una extensión algebraica y que sea algebraicamente cerrada. Ya tenemos la primera condición por el enunciado, así que vamos a comprobar la segunda.

Sea un polinomio $p(X)\in E[X]$, sabemos que los coeficientes serán algebraicos sobre $K$ puesto que $E/K$ es extensión algebraica, por lo que si $p(X)=\sum_{i=0}^{n} c_iX^i$, entonces la extensión $K(c_1,\dots c_n)/K$ es algebraica, y de hecho es finita. Si tenemos una raíz $\alpha\in E'$ ($E'$ algún cuerpo extendiendo a $K$), entonces la extensión $K(c_1,\dots c_n)(\alpha)/K$ también es finita, y tenemos un homomorfismo $\sigma:K(c_1,\dots c_n)(\alpha)/K\longrightarrow E/K$. Por ser un homomorfismo, se tiene que
$$(\sigma\circ p)(X) = \sigma\left(\sum\limits_{i=0}^{gr(p(X))} c_iX^i\right) = \sum\limits_{i=0}^{gr(p(X))} c_i\sigma(X)^i = p(\sigma(X))$$

Por tanto, $p(\sigma(\alpha)) = \sigma(p(\alpha)) = \sigma(0) = 0$, luego $\sigma(\alpha)\in E$ es una raíz del polinomio $p(X)$. Sabemos que si un polinomio tiene una raíz en un cuerpo entonces descompone en ese cuerpo, es decir, todas las raíces de $p(X)$ están en $E$. Y por esto, E es algebraicamente cerrado.

## Ejercicio 4.2

Demuestra que la clausura algebraica de $\mathbb Q$ no es una extensión finita de $\mathbb Q$.

### Resolución

Llamamos $\overline{\mathbb Q}$ a la clausura algebraica de $\mathbb Q$. Supongamos que $\mathrm{dim}_{\mathbb Q}(\overline{\mathbb Q})=n<\infty$ y entonces consideramos $\sqrt[n+1]{2}$. Es claro que $\mathrm{Irr}(\sqrt[n+1]{2}, \mathbb Q)(X)=X^{n+1}-2$, por lo que la extensión algebraica $\mathbb Q(\sqrt[n+1]{2})$ es de dimensión $n+1$ sobre $\mathbb Q$. Por ser $\overline{\mathbb Q}$ clausura algebraica ha de contener a $\mathbb Q(\sqrt[n+1]{2})$, pero $\mathrm{dim}_{\mathbb Q}(\overline{\mathbb Q})=n<n+1=\mathrm{dim}_{\mathbb Q}(Q(\sqrt[n+1]{2}))$, lo cual es imposible. Por tanto la dimensión de $\overline{\mathbb Q}$ sobre ${\mathbb Q}$ no puede ser finita.

## Ejercicio 4.3

Sea $F/K$ una extensión con $F$ algebraicamente cerrado. Si llamamos
$$ E = \left\{\alpha\in F\mid \alpha\mbox{ es algebraico sobre }K\right\},$$
demuestra que $E$ es una clausura algebraica de $K$.

### Resolución

Primero verificamos que $E$ también es un cuerpo, es decir, tenemos que comprobar que las operaciones de suma y producto son cerradas en $E$. Para ello, sean $\alpha,\beta\in E$ y consideramos las extensiones $K\subset K(\alpha)\subset K(\alpha)(\beta)\subset F$. Es claro que al menos las dos primeras extensiones son finitas, es decir, $s=\mathrm{dim}_K(K(\alpha))<\infty$ y $t=\mathrm{dim}_{K(\alpha)}(K(\alpha)(\beta))<\infty$. Esto nos dice que $\mathrm{dim}_K(K(\alpha)(\beta))=s\times t<\infty$. Entonces, lo que podemos probar, de forma más general, es que toda extensión finita es algebraica:

> Sea $K\subset K'$ con $h=\dim_K{K'}<\infty$ y sea $\varepsilon\in K'$. Forzosamente, $h+1$ elementos de $K'$ no pueden ser linealmente independientes, en particular $1,\varepsilon,\varepsilon^2,\dots \varepsilon^{h-1},\varepsilon^h$ son linealmente dependientes, equivalentemente, $\exists c_i\in K,i=1,\dots h$ tales que al menos uno de ellos no es nulo y $\sum_{i=0}^h c_i\varepsilon^i = 0$. Por tanto, el polinomio $p(X)=\sum_{i=0}^h c_iX^i$ verifica $p(\varepsilon)=0$, lo que nos dice que $\varepsilon$ es algebraico sobre $K$.

Por lo que acabamos de ver, sabiendo que $K(\alpha)(\beta)$ es una extensión finita sobre $K$ y que $\alpha+\beta,\alpha\beta\in K(\alpha)(\beta)$, tenemos que la suma y el producto de elementos algebraicos es un elemento algebraico. Luego $E$ es un cuerpo.

Ahora, para ver que $E$ es algebraicamente cerrado, sea $p(X) = \sum_{i=0}^n c_iX^i\in E[X]$ un polinomio. Ya que $F$ es algebraicamente cerrado y $p(X)\subset E[X]\subset F[X]$, existe $\alpha\in F$ raíz de $p(X)$. Veamos que $\alpha\in E$: tenemos por la definición de $E$ que todos los $c_i$ son algebraicos sobre $K$, por lo que la extensión $K(c_1,\dots c_n)/K$ es algebraica; además la extensión $K(c_1,\dots c_n)(\alpha)/K(c_1,\dots c_n)$ también lo es $\Rightarrow$ la extensión $K(c_1,\dots c_n)(\alpha)/K$ es algebraica. Esto nos dice que $\alpha\in F$ es algebraico, por lo que $\alpha\in E$. Hemos probado que $E$ es algebraicamente cerrado, y por su propia definición es una extensión algebraica de $K$, luego es una clausura algebraica de $K$.
