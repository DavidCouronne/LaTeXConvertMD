---
author: David Couronné
title: Guide katex
description: katex, latexconvertmd, utilisation katex, markdown
sidebar: auto
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

La convertion automatique avec `latexconvertmd` ne gère pas (encore) ce genre de situation.

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
$$\lim_{x \to +\infty} \frac{1}{x}=0$$
```

$$\lim_{x \to +\infty} \frac{1}{x}=0$$

::: warning Attention
Ne rien mettre avant ou après les $$
:::

Exemple:



```  md
$$\lim_{x \to +\infty} \frac{1}{x}=0$$.
```

\lim_{x \to +\infty }\frac{1}{x}=0$$.


Le problème vient du petit point après les $$ !!!


La convertion automatique avec `latexconvertmd` ne gère pas (encore) ce genre de situation.

## Problèmes rencontrés

::: danger
Katex n'est pas LaTeX !!!
:::

KaTeX est juste un moteur de rendu des environnements mathématiques en Markdown ou HTML. Mais ce n'est pas le compilateur LaTeX :)


1. Mieux vaut `matrix`que `array`
2. Katex n'aime pas le surplus d'accolades

```md
$\frac{{5}\pi}{{6}}}$
```
Ca fait planter Katex...

