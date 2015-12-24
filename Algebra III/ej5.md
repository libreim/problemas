---
title: Ejercicios Semana 5
author: David Charte
geometry: "a4paper, top=2.5cm, bottom=2.5cm, left=3cm, right=3cm"
fontsize: 10pt
header-includes:
  - \usepackage{tikz}
  - \usepackage{amsmath}
  - \providecommand{\abs}[1]{\left\lvert#1\right\rvert}
---
## Ejercicio 5.1

Calcula el grado de los cuerpos de descomposición de los siguientes polinomios sobre $\mathbb Q$:

1. $X^3-2$
1. $X^4-7$
1. $(X^2-2)(X^2-5)$

### Resolución

#### 1

Sabiendo que una raíz cúbica de la unidad es $\omega = -\frac 1 2 + \frac {\sqrt 2} 2 i\Rightarrow \omega^2 = -1-\omega$,

$$\left[\mathbb Q\left(\sqrt[3] 2, \omega\right):\mathbb Q\right] = \left[\mathbb Q\left(\sqrt[3] 2\right):\mathbb Q\right]\times \left[\mathbb Q\left(\sqrt[3] 2, \omega\right):\mathbb Q\left(\sqrt[3] 2\right)\right] = 3\times 2=6~.$$

#### 2

Las raíces del polinomio $X^4-7$ son $\pm\sqrt[4] 7,\ \pm i\sqrt[4] 7$. Es claro que generan el cuerpo $\mathbb Q(i, \sqrt[4] 7)$, que es una extensión de grado 8 sobre $\mathbb Q$:

$$\left[\mathbb Q(i, \sqrt[4] 7):\mathbb Q\right]=
\left[\mathbb Q(i, \sqrt[4] 7):\mathbb Q(i)\right] \times
\left[\mathbb Q(i):\mathbb Q\right] = 4\times 2 = 8~.$$

#### 3

Sus raíces son $\pm\sqrt 2$ y $\pm\sqrt 5$. La extensión de $\mathbb Q$ más pequeña donde el polinomio descompone es, entonces, $\mathbb Q(\sqrt 2, \sqrt 5)$ y su grado es:

$$\left[\mathbb Q(\sqrt 2, \sqrt 5):\mathbb Q\right]=
  \left[\mathbb Q(\sqrt 2, \sqrt 5):\mathbb Q(\sqrt 2)\right] \times
  \left[\mathbb Q(\sqrt 2):\mathbb Q\right] = 2\times 2 = 4~.$$

## Ejercicio 5.2

¿Es la extensión $\mathbb Q\left(\sqrt{2+\sqrt{-5}}\right)$ normal?

### Resolución

Para comprobar si es normal hemos de ver si es cuerpo de descomposición de un polinomio. El polinomio que buscamos que descomponga en la extensión es el irreducible sobre $\mathbb Q$ que tenga a $\alpha = \sqrt{2+\sqrt{-5}}$ como raíz:
$$
\alpha = \sqrt{2+\sqrt{-5}};\ \alpha^2 = {2+\sqrt{-5}};\ \alpha^2-2 = \sqrt{-5};\ \alpha^4-4\alpha^2+4=-5;\ \alpha^4-4\alpha^2+9=0~.$$

$\alpha$ es raíz de $p(X) = X^4-X^2+9$. Calculamos el resto de raíces:
$$X^2=\frac {4\pm\sqrt{16 - 36}} 2 = \frac {4\pm 2i\sqrt 5} 2=2\pm i\sqrt 5 \Rightarrow X = \pm\sqrt{2\pm i\sqrt 5}~.$$

Es claro que $\sqrt{2+ i\sqrt 5},\ -\sqrt{2+ i\sqrt 5}\in \mathbb Q(\sqrt{2+ i\sqrt 5})$ y veamos si las otras dos raíces están en la extensión.
$$(2+ i\sqrt 5)(2- i\sqrt 5)=4 - (-5) = 9\Rightarrow \sqrt{2+ i\sqrt 5}\sqrt{2- i\sqrt 5}\in \mathbb Q~,$$
luego $\sqrt{2- i\sqrt 5}$ es el inverso de $\sqrt{2+ i\sqrt 5}$ multiplicado por un racional, lo que nos dice que $\sqrt{2- i\sqrt 5}\in \mathbb Q(\sqrt{2+ i\sqrt 5})$, y por tanto $\mathbb Q(\sqrt{2+ i\sqrt 5})$ es el cuerpo de descomposición de $p(X)$, es decir, es una extensión normal sobre $\mathbb Q$.
