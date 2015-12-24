---
title: Problemas Semana 1
author: David Charte
geometry: "a4paper, top=2.5cm, bottom=2.5cm, left=3cm, right=3cm"
fontsize: 10pt
header-includes:
  \usepackage{tikz}
---

## Ejercicio 1.1
Se considera la ecuación $X^4-3=0$, con raíces $\sqrt[4]3$, $i\sqrt[4]3$, $-\sqrt[4]3$, $-i\sqrt[4]3$. Éstas generan el cuerpo $\mathbb Q(\sqrt[4]3, i)$
sobre $\mathbb Q$. Cada automorfismo de $\mathbb Q(\sqrt[4]3, i)/\mathbb Q$ envía $\sqrt[4]3$ a una de las raíces de $X^4 -3$, y envía $i$ a una
de las raíces de $X^2 + 1$. Por tanto como máximo tenemos ocho automorfismos, que forman un grupo,
y que están generados por

$$ \varphi(i)=-i,\ \varphi(\sqrt[4]3) = \sqrt[4]3,$$ {#eq:phi}
$$ \psi(i)=i,\ \psi(\sqrt[4]3) = i\sqrt[4]3.$$ {#eq:psi}

1. Prueba que $\left<\varphi,\psi\right> = \mathrm{Aut}(\mathbb Q(\sqrt[4]3, i)/\mathbb Q)$, el grupo de todos los automorfismos de la extensión $\mathbb Q(\sqrt[4]3, i)/\mathbb Q)$, es isomorfo a $D_4$, identificando $\varphi$ y $\psi$ con simetrías del cuadrado.
1. Representa por permutaciones los elementos $\varphi$ y $\psi$.
1. Dibuja el retículo de subgrupos de $D_4$ con notación de permutaciones y en función de $\varphi$ y $\psi$.
1. Observa que tiene exactamente tres subgrupos de orden 4, y cinco subgrupos de orden 2.

### Resolución

#### 1

Recordamos las relaciones fundamentales de $D_4$:

$$ D_4 = \left<r, s\ |\ r^4 = 1, s^2 = 1, sr = r^3s\right> $$

Y sabemos que si un grupo cumple estas relaciones fundamentales, entonces es
isomorfo a $D_4$. Las comprobamos:

$$\psi^4(i) = i,\ \psi^4(\sqrt[4]3) = i^4\sqrt[4]3 = \sqrt[4]3\Rightarrow\psi^4 = \mathrm{I}$$
$$\varphi^2(i) = \varphi(-i) = i,\ \varphi^2(\sqrt[4]3) = \sqrt[4]3 \Rightarrow \varphi^2 = \mathrm I$$

Luego tenemos que, identificando $\psi$ con $r$ y $\varphi$ con $s$, se cumplen las dos
primeras relaciones. Veamos la tercera:
$$(\varphi \circ \psi)(i) = \varphi(\psi(i)) = \varphi(i) = -i,\ (\varphi \circ \psi)(\sqrt[4]3) = \varphi(\psi(\sqrt[4]3)) = \varphi(i\sqrt[4]3) = -i\sqrt[4]3,$$
por otro lado,
$$ (\psi^3 \circ \varphi)(i) = \psi^3(-i) = -i,\ (\psi^3 \circ \varphi)(\sqrt[4]3) = \psi^3(\sqrt[4]3) = i^3\sqrt[4]3 = -i\sqrt[4]3.$$

Por tanto $\varphi \circ \psi=\psi^3 \circ \varphi$. Hemos comprobado que

$$ \mathrm{Aut}(\mathbb Q(\sqrt[4]3, i)/\mathbb Q) = \left<\psi,\varphi\ |\ \psi^4 = \mathrm{I}, \varphi^2 = \mathrm{I}, \varphi \circ \psi=\psi^3 \circ \varphi \right>\cong D_4.$$

#### 2

Con la representación dada en el cuadrado, $\varphi$ corresponde a la permutación $(2\ 4)$, mientras que $\psi$ corresponde a $(1\ 2\ 3\ 4)$.

#### 3

Retículo de $D_4$ en función de $\phi$ y $\psi$:

\input{d4lattice_phi}

Retículo de $D_4$ en función de las permutaciones de los vértices del cuadrado:

\input{d4lattice_perm}

#### 4

Los subgrupos $\left<\varphi, \psi^2\right>\cong C_2\times C_2\cong \left<\psi^2, \psi\circ\varphi\right>$ y $\left<\psi\right> \cong C_4$ son de orden 4, y $\left<\varphi\right>\cong \left<\psi^2\right>\cong \left<\psi\circ\varphi\right> \cong \left<\psi^2\circ\varphi\right>\cong \left<\psi^3\circ\varphi\right>\cong C_2$ de orden 2.

## Ejercicio 1.2
Dada la extensión de cuerpos $\mathbb Q(\sqrt[4]3, i)/\mathbb Q$, ya que tenemos la siguiente torre de cuerpos: $\mathbb Q \subset \mathbb Q(\sqrt[4]3) \subset \mathbb Q(\sqrt[4]3, i)$, tenemos una base de $\mathbb Q(\sqrt[4]3, i)$ sobre $\mathbb Q$ que tiene ocho elementos, y cada elemento $x\in \mathbb Q(\sqrt[4]3, i)$ se escribe de forma única como

$$ x = a_0 + a_1\sqrt[4]3 + a_2{\sqrt[4]3}^2 + a_3{\sqrt[4]3}^3 + a_4 i + a_5 i\sqrt[4]3 + a_6 i{\sqrt[4]3}^2 + a_7 i{\sqrt[4]3}^3$$ {#eq:base}

Observa que si se considera el subgrupo $\left<\psi\right>$, los elementos que quedan fijos para $\psi$ son exactamente
los que quedan fijos para cada elemento del subgrupo que $\psi$ genera.

1. Prueba que si se considera un subgrupo $H=\left<\phi_1,\dots,\phi_t\right>\subset\mathrm{Aut}(\mathbb Q(\sqrt[4]3, i)/\mathbb Q)$, un elemento $x$ queda fijo para todos los elementos de $H$ si, y solo si, queda fijo para $\phi_1,\dots,\phi_t$.
1. Prueba que el conjunto de los elementos $x$ que quedan fijos para un subgrupo $H$ es un cuerpo, al que llamaremos $F^H$, y que verifica $\mathbb Q\subset F^H\subset\mathbb Q(\sqrt[4]3,i)$.
1. Prueba que si $H_1\subset H_2\subset \mathrm{Aut}(\mathbb Q(\sqrt[4]3, i)/\mathbb Q)$ son subgrupos, entonces $F^{H_2}\subset F^{H_1}$.
1. Dibuja el retículo de los subcuerpos $F^H$, donde $H$ varía entre los subgrupos de $\mathrm{Aut}(\mathbb Q(\sqrt[4]3, i)/\mathbb Q)$.

### Resolución

#### 1

Supongamos que $x\in \mathbb Q(\sqrt[4]3, i)$ queda fijo para $H$. Por ser $\phi_1,\dots,\phi_t$ elementos de $H$, dejan fijo a $x$.

Supongamos ahora que $x\in \mathbb Q(\sqrt[4]3, i)$ queda fijo para $\phi_1,\dots,\phi_t$ y sea $\phi\in H$. Entonces, como $H$ es generado por $\phi_1,\dots,\phi_t$, $\phi$ tiene una expresión como composición de estas funciones, y puesto que $x$ queda fijo para todas ellas, queda fijo para la composición, es decir, $\phi$.

#### 2

Nos basta comprobar que $F^H$ es cerrado para la suma y el producto para saber que es un subcuerpo de $\mathbb Q(\sqrt[4]3, i)$ y, por tanto, un cuerpo. Sean $x,y\in F^H, \phi\in H$. Por ser $\phi$ un automorfismo en $\mathbb Q(\sqrt[4]3, i)$:

* $\phi(x + y) = \phi(x) + \phi(y) = x + y$
* $\phi(x \times y) = \phi(x) \times \phi(y) = x \times y$

Luego $F^H$ es un cuerpo.

#### 3

Veamos que cada elemento que queda fijo para los elementos de $H_2$ queda fijo para los elementos de $H_1$. Sea $x\in F^{H_2}$ y sea $\phi\in H_1\subset H_2\Rightarrow \phi(x) = x\mbox{ (por estar }\phi\mbox{ en }H_2\mbox{)}\Rightarrow x\in F^{H_1}$.

#### 4

Veamos qué cuerpos se componen de los puntos fijos para cada subgrupo de $\mathrm{Aut}(\mathbb Q(\sqrt[4]3, i)/\mathbb Q)$:

* $\{\mathrm I\}$ deja fijo $\mathbb Q(\sqrt[4]3, i)$.
* $\left<\varphi\right>$ solamente mueve $i$, luego deja fijo $\mathbb Q(\sqrt[4]3)$.
* $\left<\psi^2\circ\varphi\right>$ deja fijos los elementos de $\mathbb Q({\sqrt[4]3}^2, i\sqrt[4]3)$:
\begin{align*}
x &= a_0 + a_1{\sqrt[4]3} + a_2{\sqrt[4]3}^2 + a_3{\sqrt[4]3}^3+a_4i+a_5i{\sqrt[4]3}+a_6i{\sqrt[4]3}^2+a_7i{\sqrt[4]3}^3, \\
(\psi^2\circ\varphi)(x) &= a_0 - a_1{\sqrt[4]3} + a_2{\sqrt[4]3}^2 - a_3{\sqrt[4]3}^3-a_4i+a_5i{\sqrt[4]3}-a_6i{\sqrt[4]3}^2+a_7i{\sqrt[4]3}^3, \\
(\psi^2\circ\varphi)(x) &= x \Rightarrow a_1 = a_3 = a_4 = a_6 = 0.
\end{align*}

* $\left<\psi^2\right>$ deja fijos tanto $i$ como ${\sqrt[4]3}^2$, es decir, el cuerpo $\mathbb Q({\sqrt[4]3}^2, i)$.
* $\left<\psi\circ\varphi\right>$ deja fijos los elementos del tipo $a_0+a_1(1+i)\sqrt[4]3+a_3(1-i){\sqrt[4]3}^3+a_6i{\sqrt[4]3}^2$:
\begin{align*}
x &= a_0 + a_1{\sqrt[4]3} + a_2{\sqrt[4]3}^2 + a_3{\sqrt[4]3}^3+a_4i+a_5i{\sqrt[4]3}+a_6i{\sqrt[4]3}^2+a_7i{\sqrt[4]3}^3, \\
(\psi\circ\varphi)(x) &= a_0 + a_1i{\sqrt[4]3} - a_2{\sqrt[4]3}^2 - a_3i{\sqrt[4]3}^3-a_4i+a_5{\sqrt[4]3}+a_6i{\sqrt[4]3}^2-a_7{\sqrt[4]3}^3, \\
(\psi\circ\varphi)(x) &= x \Rightarrow a_2 = a_4 = 0,\ a_1 = a_5,\ a_3 = -a_7.
\end{align*}

* $\left<\psi^3\circ\varphi\right>$ deja fijos los elementos del tipo $a_0+a_1(1-i)\sqrt[4]3+a_3(1+i){\sqrt[4]3}^3+a_6i{\sqrt[4]3}^2$, análogamente al caso anterior.
* $\left<\psi^2, \varphi\right>$ deja fija la intersección de los cuerpos correspondientes a $\left<\psi^2\right>$ y $\left<\varphi\right>$, es decir, $\mathbb Q({\sqrt[4]3}^2)$.
* $\left<\psi\right>$ únicamente deja fija $i$, corresponde a $\mathbb Q(i)$.
* $\left<\psi^2, \psi\circ\varphi\right>$ únicamente puede dejar fijos los elementos del tipo $a_0 +a_6i{\sqrt[4]3}^2$, ya que son la intersección de los correspondientes cuerpos.
* $\left<\psi,\varphi\right>$ puede mover cualquier elemento excepto los del cuerpo $\mathbb Q$.

Tenemos el siguiente retículo con la relación de inclusión entre los cuerpos:

\input{d4lattice_inv}

## Ejercicio 1.3

Escribir, en función de los polinomios simétricos elementales en $X , Y, Z$, el polinomio $p(X , Y, Z) = X^4 + Y^4 + Z^4 \in\mathbb Q[X , Y, Z]$. Detallar, paso a paso, la aplicación del algoritmo.

### Resolución

$$ e_1 = \underline{X} = X + Y + Z,\ e_2 = \underline{XY} = XY + XZ+YZ,\ e_3 = XYZ$$

El primer término del polinomio $p$, siguiendo el orden lexicográfico, es $X^4$. Para eliminarlo hemos de tomar $e_3$ con el exponente de la variable $Z$, es decir, 0; $e_2$ con el de la $Y$ menos el anterior (0 de nuevo), y finalmente $e_1$ con el exponente de la $X$ menos los anteriores, 4. En resumen, estaremos tomando $e_1^4$, de forma que
$$p - e_1^4 = X^4 + Y^4 + Z^4 - (X+Y+Z)^4 = -4 \underline{X^3 Y}-6 \underline{X^2 Y^2}-12 \underline{X^2 Y Z}$$

Ahora el primer término es $-4X^3Y$, por lo que, de nuevo, tenemos exponente 0 en la $Z$, ahora el exponente de la $Y$ es 1 (tomamos $e_2$), y el de la $X$ es 3 (tomamos $e_1^2$). Utilizamos el coeficiente opuesto al del término $-4X^3Y$, es decir, $4$, para que la diferencia sea 0:

$$p - e_1^4 +4 e_1^2e_2 = X^4 + Y^4 + Z^4 - (X+Y+Z)^4 + 4(X+Y+Z)^2(XY+XZ+YZ) =$$
$$ =-4 \underline{X^3 Y}-6 \underline{X^2 Y^2}-12 \underline{X^2 Y Z} + 4\underline{X^3Y} + 8\underline{X^2Y^2} + 20\underline{X^2YZ} =2\underline{X^2Y^2}+8\underline{X^2YZ}$$

Tomamos ahora el nuevo término $2X^2Y^2$, y para eliminarlo utilizamos el polinomio $e_2$ elevándolo al cuadrado puesto que el exponente de $Y$ es 2, y el exponente de $e_1$ nos queda 0:

$$p - e_1^4 +4 e_1^2e_2 -2e_2^2 = X^4 + Y^4 + Z^4 - \underline{X}^4 + 4\underline{X}^2\underline{XY} - 2\underline{XY}^2 =$$
$$=2\underline{X^2Y^2}+8\underline{X^2YZ} - 2\underline{X^2Y^2} - 4 \underline{X^2YZ}=4 \underline{X^2YZ}$$

Nos queda por último el término $4X^2YZ$, que eliminaremos utilizando $e_3$ elevado a 1 ($Z$ tiene exponente 1), $e_2$ elevado a 0 y $e_1$ elevado a 1:

$$p - e_1^4 +4 e_1^2e_2 -2e_2^2 -4e_1e_3 = X^4 + Y^4 + Z^4 - \underline{X}^4 + 4\underline{X}^2\underline{XY} - 2\underline{XY}^2 - 4\underline{X}~\underline{XYZ} =$$
$$=4 \underline{X^2YZ} - 4\underline{X^2YZ} = 0$$

En conclusión, tenemos la descomposición siguiente:

$$p = e_1^4 -4 e_1^2e_2 +2e_2^2 +4e_1e_3= \underline{X}^4 - 4\underline{X}^2\underline{XY} + 2\underline{XY}^2 + 4\underline{X}~\underline{XYZ}$$
