---
title: Ejercicios Semana 3
author: David Charte
geometry: "a4paper, top=2.5cm, bottom=2.5cm, left=3cm, right=3cm"
fontsize: 10pt
header-includes:
  - \usepackage{tikz}
  - \usepackage{amsmath}
  - \providecommand{\abs}[1]{\left\lvert#1\right\rvert}
---

## Ejercicio 3.1

Sea $F$ un cuerpo finito de característica $p$. Demuestra que $\abs F=p^n$ para algún entero positivo $n$.

### Resolución

Sea $F$ cuerpo verificando $\mathrm{car}(F)=p\Rightarrow1+1+\dots\mbox{(}p\mbox{ veces)}+1 = 0$. Sabemos que $p$ será un número primo, puesto que de lo contrario tendríamos divisores de cero en $F$, contradiciendo el hecho de que sea un dominio de integridad.

Podemos construir un monomorfismo $h: \mathbb Z_p\longrightarrow F$ y consideramos $\mathrm{Im}(h)\cong \mathbb Z_p$. Vemos entonces que $F$ es un espacio vectorial finito sobre $\mathrm{Im}(h)$ y por tanto tendrá una base con $n\in \mathbb Z^+$ elementos, lo que nos dice que $\abs F=p^n$.

## Ejercicio 3.2

Razona, sabiendo que $\pi$ y $e$ son trascendentes, cuáles de los siguientes números complejos son algebraicos o trascendentes sobre $\mathbb Q$.

1. $\sqrt 7$
1. $\sqrt[3] 3$
1. $\pi^2$
1. $e^3 + 1$
1. $\sqrt i + 2$

### Resolución

#### 1
Sabemos que $\sqrt 7$ es raíz del polinomio $X^2-7\in\mathbb Q[X]$, luego es algebraico sobre $\mathbb Q$.

#### 2
De forma similar a lo anterior, $\sqrt[3] 3$ es una raíz del polinomio $X^3 - 3\in\mathbb Q[X]$ por lo que es algebraico.

#### 3
Supongamos que $\pi^2$ fuera algebraico. Entonces sería raíz de un polinomio $p(X)\in\mathbb Q[X]$. Supongamos que el polinomio $p(X)$ tiene la siguiente expresión:
$$p(X) = \displaystyle\sum\limits_{i=0}^n c_iX^i,\ c_i\in\mathbb Q\ \forall i\in\{0,\dots n\},\ c_n\neq 0.$$ {#eq:polexpr}

Entonces, definamos un polinomio $q(X)$ con la siguiente expresión:
$$q(X)=\displaystyle\sum\limits_{i=0}^n c_i(X^2)^i = \displaystyle\sum\limits_{i=0}^n c_iX^{2i}\in\mathbb Q[X].$$

Es claro que $q(\pi)=p(\pi^2)=0$, luego $\pi$ es raíz de un polinomio en $\mathbb Q$, lo cual contradice que sea trascendente. Por tanto, $\pi^2$ no puede ser algebraico, ha de ser trascendente.

#### 4
Trabajaremos de la misma forma que en el apartado anterior. Si $e^3+1$ es algebraico, será raíz de un polinomio $p(X)$, y supondremos que este se escribe como la expresión dada en (@eq:polexpr). En ese caso podemos definir el siguiente polinomio:
$$q(X)=\displaystyle\sum\limits_{i=0}^n c_i(X^3+1)^i = \displaystyle\sum\limits_{i=0}^n c_i\left(\sum\limits_{k=0}^i\binom{i}{k}X^{k}\right)\in\mathbb Q[X].$$

Y podemos observar que $q(e)=p(e^3+1)=0$, en cuyo caso $e$ sería raíz del polinomio $q(X)$, contradiciendo que sea trascendente. Por esto, $e^3+1$ también es trascendente.

#### 5
Si trabajamos con la igualdad $X = \sqrt i + 2$ podemos llegar a un polinomio con coeficientes en $\mathbb Q$ que tenga a $\sqrt i + 2$ como raíz:
$$ X = \sqrt i + 2\Rightarrow X-2=\sqrt i\Rightarrow (X-2)^4 = -1\Rightarrow  X^4-8X^3+24X^2-32X+17=0$$

Llegamos a que $\sqrt i + 2$ es una raíz del polinomio $X^4-8X^3+24X^2-32X+17\in\mathbb Q[X]$, luego es un elemento algebraico.

## Ejercicio 3.3

Demuestra que el polinomio $f(X) = X^3+3X+1$ es irreducible en $\mathbb Q[X]$. Si $\alpha$ es una raíz de $f(X)$ en una extensión de $\mathbb Q$, calcula $(1+\alpha)(1+\alpha+\alpha^2)$ y $(1+\alpha)/(1+\alpha+\alpha^2)$.

### Resolución

Por el lema de Gauss, puesto que $\mathbb Q$ es el cuerpo de fracciones de $\mathbb Z$ y este un dominio de factorización única, nos basta ver que $f(X)$ no tiene raíces enteras. Primero vemos que $0$ no es raíz ($f(0)=1$), y tampoco lo son $1$ ($f(1)=5$) ni $-1$ ($f(-1)=-3$). Ahora supongamos que $n\in\mathbb Z\mbox{ con}\abs n>1$ es raíz de $f(X)$, es decir, se tiene:
$$n^3+3n+1=0\Rightarrow n(n^2+3)=-1\Rightarrow n^2=-3-\frac{1}{n}\notin\mathbb Z\Rightarrow n\notin\mathbb Z\mbox{ (contradicción).}$$

Hemos comprobado que ningún entero es raíz de $f(X)$. Por esto, el polinomio es irreducible en $\mathbb Z[X]$ y también lo es en $\mathbb Q[X]$.

$$(1+\alpha)(1+\alpha+\alpha^2) = \alpha^3+2\alpha^2+2\alpha+1 = (\alpha^3+3\alpha+1) +2\alpha^2-\alpha = 2\alpha^2-\alpha\in\mathbb Q(\alpha)~.$$

$$\frac{1+\alpha}{1+\alpha+\alpha^2}=a+b\alpha+c\alpha^2\Rightarrow 1+\alpha = (a+b\alpha+c\alpha^2)(1+\alpha+\alpha^2) =$$
$$= a+(a+b)\alpha+(a+b+c)\alpha^2+(b+c)\alpha^3+c\alpha^4~.$$

Para cancelar el término en $\alpha^4$, sabemos que $0 = c\alpha(\alpha^3+3\alpha+1)$ por lo que podemos restarlo en la expresión:
$$1+\alpha = a+(a+b-c)\alpha+(a+b-2c)\alpha^2+(b+c)\alpha^3~,$$
y repetir el paso con $0=(b+c)(\alpha^3+3\alpha+1)$ para eliminar el término en $\alpha^3$:
$$1+\alpha = a-b-c+(a-2b-4c)\alpha+(a+b-2c)\alpha^2~.$$

Obtenemos el siguiente sistema de ecuaciones lineales:
$$\begin{cases}
a-b-c&=1\\
a-2b-4c&=1\\
a+b-2c&=0
\end{cases}\ \Rightarrow\
\begin{cases}
a-b-c&=1\\
 b+3c&=0\\
-7c&=-1
\end{cases}\ \Rightarrow\
\begin{cases}
a=\frac 5 7\\
b=-\frac 3 7\\
c=\frac 1 7
\end{cases}$$

Por tanto, tenemos que
$$\frac{1+\alpha}{1+\alpha+\alpha^2}=\frac 5 7 - \frac 3 7\alpha + \frac 1 7\alpha^2\in\mathbb Q(\alpha)~.$$

## Ejercicio 3.4

Calcula $\mathrm{Irr}(\alpha, \mathbb Q)$ en los siguientes casos:

1. $\alpha = 2+\sqrt 5$
1. $\alpha= \sqrt[4] 5 + \sqrt 5$
1. $\alpha = \sqrt[3] 2 + \sqrt[3] 4$

Da en cada caso una $\mathbb Q$-base de $F=\mathbb Q(\alpha)$.

### Resolución

#### 1
Observamos que $\alpha^2 = 9 + 8\sqrt 5 = 8(2 + \sqrt 5) - 7$ no es linealmente independiente de $\{1, 2+\sqrt 5\}$, por lo que la extensión es de grado 2 y un polinomio de grado 2 que tenga a $\alpha$ como raíz será irreducible:
$$\alpha-2=\sqrt 5;\ \alpha^2-4\alpha+4=5;\ \alpha^2-4\alpha-1=0$$

$\alpha=2 + \sqrt 5$ es raíz del polinomio $\mathrm{Irr}(\alpha, \mathbb Q)=X^2-4X-1\in\mathbb Q[X]$. Una $\mathbb Q$-base de $\mathbb Q(2+\sqrt 5)$ es $\{1, 2+\sqrt 5\}$ o, simplemente, $\{1, \sqrt 5\}$.

#### 2
Trabajamos con la igualdad $\alpha = \sqrt[4] 5 + \sqrt 5$:
$$\alpha - \sqrt 5 = \sqrt[4] 5;\ \alpha^2 + 5 - 2\alpha\sqrt 5 = \sqrt 5;\ \alpha^2 + 5 = \sqrt 5(1 + 2\alpha);$$
$$\alpha^4 + 25 + 10\alpha^2 = 5(1 + 4\alpha^2 + 4\alpha);\ \alpha^4-20\alpha^2-20\alpha+20=0$$
Tenemos que $\sqrt[4] 5 +\sqrt 5$ es raíz del polinomio $p(X)=X^4-20X^2-20X+20\in\mathbb Q[X]$. Todos los coeficientes menos el líder son múltiplos de 5, por lo que el criterio de Eisenstein nos dice que $p(X)$ es irreducible. Por tanto, la extensión $\mathbb Q\subset\mathbb Q(\sqrt[4] 5 +\sqrt 5)=\mathbb Q(\sqrt[4] 5)$ es de grado 4 y una base es $\{1, \sqrt[4] 5, \sqrt 5, \sqrt[4] {5^3}\}$.

#### 3
Estudiamos $\alpha = \sqrt[3] 2 + \sqrt[3] 4$:
$$\alpha = \sqrt[3] 2 + \sqrt[3] 4 = \sqrt[3] 2 \left( 1 + \sqrt[3] 2\right);\ \alpha^3=2\left(1 + 2 + 3\sqrt[3] 2 + 3\sqrt[3] {2^2}\right)=6(1 + \sqrt[3] 2 + \sqrt[3] {2^2}) = 6(1+\alpha)\Rightarrow$$
$$\Rightarrow \alpha^3-6\alpha-6 = 0 $$

Hemos visto que $\alpha$ es raíz de $p(X)=X^3-6X-6\in\mathbb Q[X]$. Por el criterio de Eisenstein, de nuevo, es claro que es irreducible. La extensión $\mathbb Q\subset \mathbb Q(\sqrt[3] 2 + \sqrt[3] 4) = \mathbb Q(\sqrt[3] 2)$ es de grado 3 y una base es $\{1, \sqrt[3] 2, \sqrt[3] 4\}$.
