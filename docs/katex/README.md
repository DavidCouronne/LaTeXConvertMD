---
sidebar: auto
title: Guide Katex
---

# Syntaxe de base

## Maths en ligne

```md
$\sqrt{2}$
```

$\sqrt{2}$

::: warning Attention
Il faut bien "coller" les $ à l'expression !
:::

Exemple:

``` md
$\sqrt{2} $
```

$\sqrt{2} $

La convertion automatique avec `latexconvertmd` ne gère pas (encore) ce genre de situations.

::: tip Astuce
On peut "passer à la ligne" !
:::

``` md
$f(x)=(x-1)(x+2)\\
\phantom{f(x)}=x^2+2x-x-2\\
\phantom{f(x)}=x^2+x-2$
```

$f(x)=(x-1)(x+2)\\
\phantom{f(x)}=x^2+2x-x-2\\
\phantom{f(x)}=x^2+x-2$

## Maths en block

```  md
$$\lim{x \to +\infty \frac{1}{x}=0}$$
```

$$\lim{x \to +\infty \frac{1}{x}=0}$$

::: warning Attention
Ne rien mettre avant ou après les $$
:::

Exemples:

```  md
$$\lim{x \to +\infty \frac{1}{x}=0} $$
```

$$\lim{x \to +\infty \frac{1}{x}=0} $$

```  md
$$\lim{x \to +\infty \frac{1}{x}=0}$$.
```

$$\lim{x \to +\infty \frac{1}{x}=0}$$.
