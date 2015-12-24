---
title: Problemas Semana 2
author: David Charte
geometry: "a4paper, top=2.5cm, bottom=2.5cm, left=3cm, right=3cm"
fontsize: 10pt
header-includes:
  - \usepackage{tikz}
  - \usepackage{amsmath}
---

## Ejercicio 2.1

Si $\alpha_1$, $\alpha_2$, $\alpha_3$ son las raíces del polinomio $X^3+aX^2+bX+c\in\mathbb Q[X]$, determina los coeficientes de un polinomio cuyas raíces son las que se expresan en cada caso.

1. $\alpha_1+\alpha_2,\alpha_2+\alpha_3\mbox{ y }\alpha_3+\alpha_1$
1. $\alpha_1^2+\alpha_2^2,\alpha_2^2+\alpha_3^2\mbox{ y }\alpha_3^2+\alpha_1^2$

### Resolución

Podemos determinar los coeficientes de un polinomio en función de los polinomios simétricos elementales de sus raíces. Lo haremos en general para polinomios de grado 3:

Si $p(X)\in \mathbb Q[X]$ tiene raíces $\alpha, \beta, \gamma$, entonces se expresa como
\begin{align*}
p(X) &= (X-\alpha)(X-\beta)(X-\gamma)\\&=X^3-(\alpha+\beta+\gamma)X^2+(\alpha\beta+\alpha\gamma+\beta\gamma)X-\alpha\beta\gamma\\&=X^3-e_1X^2+e_2X-e_3
\end{align*}

En el caso del enunciado, por tanto, se dan las siguientes igualdades:
$$ a = -e_1,\ b = e_2,\ c=-e_3$$

#### 1
Los polinomios simétricos elementales para las nuevas raíces se pueden expresar en función de $e_1,e_2,e_3$, puesto que también son polinomios simétricos en las raíces originales:

$$ (\alpha_1+\alpha_2)+(\alpha_1+\alpha_3)+(\alpha_2+\alpha_3) = 2(\alpha_1+\alpha_2+\alpha_3) = 2e_1;$$
$$ (\alpha_1+\alpha_2)(\alpha_1+\alpha_3)+(\alpha_1+\alpha_2)(\alpha_2+\alpha_3)+(\alpha_1+\alpha_3)(\alpha_2+\alpha_3) = $$
$$=\alpha_1^2+\alpha_2^2+\alpha_3^2+3(\alpha_1\alpha_2+\alpha_1\alpha_3+\alpha_2\alpha_3)=e_1^2+e_2;$$
$$(\alpha_1+\alpha_2)(\alpha_1+\alpha_3)(\alpha_2+\alpha_3) = \alpha_1^2\alpha_2+\alpha_1^2\alpha_3+\alpha_2^2\alpha_1+\alpha_2^2\alpha_3+\alpha_3^2\alpha_1+\alpha_3^2\alpha_2+2\alpha_1\alpha_2\alpha_3=$$
$$=e_1e_2-\alpha_1\alpha_2\alpha_3=e_1e_2-e_3~.$$

Por tanto, si $\alpha_1+\alpha_2,\alpha_2+\alpha_3\mbox{ y }\alpha_3+\alpha_1$ son las raíces de $X^3+AX^2+BX+C$, tenemos las siguientes igualdades:

$$ A = -2e_1 = -2(-a) = 2a,\ B = e_1^2+e_2 = a^2+b,\ C = -(e_1e_2-e_3) = ab-c~.$$

#### 2

Procedemos de forma análoga al apartado anterior:

$$ (\alpha_1^2+\alpha_2^2)+(\alpha_1^2+\alpha_3^2)+(\alpha_2^2+\alpha_3^2) = 2(\alpha_1^2+\alpha_2^2+\alpha_3^2) = 2(e_1^2-2e_2);$$
$$ (\alpha_1^2+\alpha_2^2)(\alpha_1^2+\alpha_3^2)+(\alpha_1^2+\alpha_2^2)(\alpha_2^2+\alpha_3^2)+(\alpha_1^2+\alpha_3^2)(\alpha_2^2+\alpha_3^2) = $$
$$=\alpha_1^4+\alpha_2^4+\alpha_3^4+3(\alpha_1^2\alpha_2^2+\alpha_1^2\alpha_3^2+\alpha_2^2\alpha_3^2)=e_1^4-4e_1^2e_2+5e_2^2-2e_1e_3;$$
$$(\alpha_1^2+\alpha_2^2)(\alpha_1^2+\alpha_3^2)(\alpha_2^2+\alpha_3^2) = \alpha_1^4\alpha_2^2+\alpha_1^4\alpha_3^2+\alpha_2^4\alpha_1^2+\alpha_2^4\alpha_3^2+\alpha_3^4\alpha_1^2+\alpha_3^4\alpha_2^2+2\alpha_1^2\alpha_2^2\alpha_3^2=$$
$$=e_1^2e_2^2-2e_1^3e_3-2e_2^3+4e_1e_2e_3-e_3^2.$$

Por tanto, si $\alpha_1^2+\alpha_2^2,\alpha_2^2+\alpha_3^2\mbox{ y }\alpha_3^2+\alpha_1^2$ son las raíces de $X^3+AX^2+BX+C$, tenemos las siguientes igualdades:
\begin{align*}
 A &= -2(e_1^2-2e_2) = -2((-a)^2-2b) = 4b-2a^2,\\
 B &= e_1^4-4e_1^2e_2+5e_2^2-2e_1e_3 = (-a)^4-4(-a)^2b+5b^2-2(-a)(-c) = a^4-4a^2b+5b^2-2ac,\\
 C &= -(e_1^2e_2^2-2e_1^3e_3-2e_2^3+4e_1e_2e_3-e_3^2) = -(a^2b^2-2a^3c-2b^3+4abc-c^2).
\end{align*}

## Ejercicio 2.2

Determinar todas las ternas de números $a,b,c$ tales que su suma es $-3$, la suma de sus cuadrados es $6$, y la suma de sus cubos es $-3$.

### Resolución

<!--Buscamos las raíces comunes a los polinomios
$$ p_1 = a+b+c+3,\ p_2 = a^2+b^2+c^2-6,\ p_3 = a^3+b^3+c^3+3 $$
-->

Buscamos ternas $(a, b, c)$ soluciones al sistema
\begin{equation*}
\begin{cases}
  a+b+c&=-3 \\
  a^2+b^2+c^2&=6 \\
  a^3+b^3+c^3&=-3
\end{cases}
\end{equation*}

Para ello podemos calcular las raíces del siguiente polinomio:
$$p(X) = (X-a)(X-b)(X-c)=X^3-(a+b+c)X^2+(ab+ac+bc)X-abc=X^3-e_1X^2+e_2X-e_3$$

Observamos que los polinomios del sistema homogéneo (sin considerar los términos
  independientes) son simétricos, luego los podemos expresar en función de los polinomios
  simétricos elementales:

\begin{align*}
  a+b+c &= e_1 = -3 \\
  a^2+b^2+c^2 &= e_1^2 - 2e_2 = 6 \\
  a^3+b^3+c^3 &= e_1^3 - 3e_1e_2 +3e_3 = -3
\end{align*}

Y despejamos los valores para $e_1\mbox{, }e_2\mbox{ y }e_3$:

$$e_1 = -3 \Rightarrow e_2 = \frac{6-(-3)^2}{-2}=\frac 3 2\Rightarrow e_3 = \frac{-3-\frac{27}{2}+27}{3}=\frac {7}{2}.$$

Entonces tenemos el polinomio $p$ desarrollado como:
$$p(X) = X^3+3X^2+\frac 3 2 X -\frac 7 2$$

Puesto que es de grado 3, podemos calcular las raíces programáticamente. Las raíces del polinomio formarán las posibles ternas $(a,b,c)$ intercambiándolas entre ellas, dada la naturaleza simétrica del problema:

$$\{a, b, c\} =
\begin{Bmatrix}
-1+\frac 1 6 \sqrt[3]{324-54 \sqrt{34}}+\frac{\sqrt[3]{6+\sqrt{34}}}{2^\frac 2 3},\\
-1-\frac 1{12}(1-i\sqrt 3)\sqrt[3]{324-54\sqrt{34}}-\frac{(1+i\sqrt 3)\sqrt[3]{6+\sqrt{34}}}{2\times 2^\frac 2 3},\\
-1-\frac 1{12}(1+i\sqrt 3)\sqrt[3]{324-54\sqrt{34}}-\frac{(1-i\sqrt 3)\sqrt[3]{6+\sqrt{34}}}{2\times 2^\frac 2 3}
\end{Bmatrix}$$

## Ejercicio 2.3

Si las raíces del polinomio $X^3+X^2-X-k$ son $\alpha_1,\alpha_2,\alpha_3$, que verifican la relación $\alpha_1^2-\alpha_2^2+\alpha_3^2=0$, ¿cuáles son los posibles valores de $k$?

### Resolución

Sabemos que el coeficiente independiente del polinomio es $-e_3 = \alpha_1\alpha_2\alpha_3$. Por tanto, $k = e_3$.
Por la relación $\alpha_1^2-\alpha_2^2+\alpha_3^2=0$, no es difícil calcular el valor de $\alpha_2$. Si llamamos $E = \alpha_1^2+\alpha_2^2+\alpha_3^2$, tenemos:
$$\alpha_1^2-\alpha_2^2+\alpha_3^2=0\Rightarrow\alpha_1^2+\alpha_2^2+\alpha_3^2 - 2\alpha_2^2 = 0\Rightarrow \alpha_2=\pm\sqrt{\frac{E}{2}}~.$$

Por otro lado,
$$E = e_1^2-2e_2 = (-1)^2-2(-1) = 3~.$$

Luego $\alpha_2 = \pm\sqrt{\frac{3}{2}}$. Ahora buscamos el valor de $\alpha_1\alpha_3$, para ello podemos usar el valor de $e_2$ dado por el polinomio:

$$ e_2 = \alpha_1\alpha_2+\alpha_1\alpha_3+\alpha_2\alpha_3 = -1\Rightarrow \alpha_1\alpha_3 = -1 -\alpha_2(\alpha_1+\alpha_3)$$

Buscamos el valor de $(\alpha_1+\alpha_3)$ dado por $e_1$:

$$ e_1 = \alpha_1+\alpha_2+\alpha_3=-1\Rightarrow \alpha_1+\alpha_3 = -1-\alpha_2\Rightarrow \alpha_1\alpha_3 = -1 -\alpha_2(-1-\alpha_2)\Rightarrow$$
$$\Rightarrow k = (\alpha_1\alpha_3)\alpha_2 = (-1 -\alpha_2(-1-\alpha_2))\alpha_2~,$$

y usamos los dos valores de $\alpha_2$ para encontrar los valores de $k$:
$$\alpha_2 = \sqrt\frac 3 2\Rightarrow k = \left(-1 -\sqrt\frac 3 2\left(-1-\sqrt\frac 3 2\right)\right)\sqrt\frac 3 2 = \frac{3 + \sqrt \frac 3 2}{2}$$
$$\alpha_2 = -\sqrt\frac 3 2\Rightarrow k = \left(-1 +\sqrt\frac 3 2\left(-1+\sqrt\frac 3 2\right)\right)\left(-\sqrt\frac 3 2\right) = \frac{3 - \sqrt \frac 3 2}{2}$$
