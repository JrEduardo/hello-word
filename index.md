---
title       : Distribuição COM-Poisson 
subtitle    : Dados de Contagem Sub e Superdispersos
author      : Eduardo Junior
job         : PET-Estatística
biglogo     : PET800x600.png
logo        : PETsmall.png
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : solarized_light  # {tomorrow, solarized_light, ...}
widgets     : [mathjax, quiz, bootstrap]     # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft, selfcontained}
knit        : slidify::knit2slides
---




--- .segue bg:gray

## Introdução

---
## Dados de Contagem

> - Variável aleatória discreta
> - Assume somente um número enumerável de valores (finito ou infinito)
> - Representam o número de ocorrências de um evento em um intervalo de tempo ou espaço

> - Exemplos:
    > - Número de sinistros em um ano
    > - Número de ligações por mês em uma empresa de telefonia
    > - Número de frutos obtidos em uma árvore

---

## Distribuição de Probabilidades

> - <img src="/home/eduardojr/Dropbox/Graduação/FinalWork/Preliminary/Siepe2015/Seminarios_Discentes/Slide/assets/img/px.png" align="middle" height="450" width="650" margin="0 auto" />

> - 
<img src="assets/fig/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto auto auto 0;" />

--- .segue bg:gray

## Modelando Dados de Contagem

---

## Modelo Probabilístico Poisson

> - Função distribuição de probabilidade
    >  $$\begin{matrix}
    P(Y = y ; \lambda) = \frac{e^{-\lambda}\lambda^{y}}{y!} &  \text{  } \lambda > 0 
    \end{matrix}$$

> - Características:
    >  $E[Y] = \lambda$<p>
    >  $V[Y] = \lambda$

---

<iframe width="600" height="300" frameborder="0" scrolling="no" marginheight="0" marginwidth="0"
   src="http://200.17.213.89:3838/eduardo/pois">
</iframe>

---

--- .segue bg:gray

## Distribuição COM-Poisson

---

## Modelo Probabilístico COM - Poisson

> - Richard Conway e William Maxwell (1962)

> - Função distribuição de probabilidade
    >  $$\begin{align*}
    P(Y = y; \lambda,& \nu) = \frac{\lambda^{y}}{(y!)^{\nu}Z(\lambda, \nu)} \qquad \lambda > 0, \nu \geqslant 0\\
    &Z(\lambda, \nu) = \sum_{j=0}^{\infty}\frac{\lambda^{j}}{(j!)^{\nu}}    
    \end{align*}$$

> - Características:
    >  $E[Y] = \sum_{j=0}^{\infty}\frac{j\lambda^{j}}{(j!)^{\nu} Z(\lambda, \nu)}$<p>
    >  $V[Y] = \sum_{j=0}^{\infty}\frac{j^2\lambda^{j}}{(j!)^{\nu} Z(\lambda, \nu)} - E^2[Y]$

---

## Vantagens



<img src="assets/fig/unnamed-chunk-4-1.png" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" style="display: block; margin: auto;" />

---

## Vantagens

<img src="assets/fig/unnamed-chunk-5-1.png" title="plot of chunk unnamed-chunk-5" alt="plot of chunk unnamed-chunk-5" style="display: block; margin: auto;" />

---

## Vantagens

<img src="assets/fig/unnamed-chunk-6-1.png" title="plot of chunk unnamed-chunk-6" alt="plot of chunk unnamed-chunk-6" style="display: block; margin: auto;" />

---

## Vantagens

<img src="assets/fig/unnamed-chunk-7-1.png" title="plot of chunk unnamed-chunk-7" alt="plot of chunk unnamed-chunk-7" style="display: block; margin: auto;" />

---

## Vantagens

> -  Pertence à família exponencial de distribuições

> - Tem como casos particulares os modelos:
    > - Poisson ($\nu = 1$)
    > - Bernoulli ($\nu = \infty$)
    > - Geométrica ($\nu = 0$ e $lambda < 1$) 

---

<iframe width="600" height="300" frameborder="0" scrolling="no" marginheight="0" marginwidth="0"
   src="http://200.17.213.89:3838/eduardo/com-pois">
</iframe>

---

## Desvantagens

> - $Z(\lambda, \nu) = \sum_{j=0}^{\infty}\frac{\lambda^{j}}{(j!)^{\nu}}$<p>
Quando $\nu = 0$ e $\lambda \geqslant 0$ não converge

> - Restrição no espaço paramétrico

> - Metódo de estimação por máxima verossimilhança é instável

---

## Desvantagens



<img src="assets/fig/unnamed-chunk-9-1.png" title="plot of chunk unnamed-chunk-9" alt="plot of chunk unnamed-chunk-9" style="display: block; margin: auto;" />

>  Subdispersão ($\lambda$ = 5.66 e $\nu$ = 1.5)

---

## Desvantagens

<img src="assets/fig/unnamed-chunk-10-1.png" title="plot of chunk unnamed-chunk-10" alt="plot of chunk unnamed-chunk-10" style="display: block; margin: auto;" />

>  Superdispersão ($\lambda$ = 1.56 e $\nu$ = 0.5)

---

## Desvantagens

<img src="assets/fig/unnamed-chunk-11-1.png" title="plot of chunk unnamed-chunk-11" alt="plot of chunk unnamed-chunk-11" style="display: block; margin: auto;" />

>  Equidispersão ($\lambda$ = 3 e $\nu$ = 1)

--- .segue bg:gray

## Propostas

---

## Métodos de Estimação

> 1. Comparar abordagens para máximização da log-verossimilhança
> 2. Estimar via mínimos quadrados ponderados
> 3. Estimar via abordagem bayesiana

---

## Modelos de Regressão

> 1. Comparar os modelos COM-Poisson com outras abordagens utilizadas (quasi-verossimilhança, binomial negativo, etc)

---

## Aspecto Computacional

 1. Implementar os métodos de estimação e comparação de modelos no software R.
 
  > - **compoisson** (Jeffrey Dunn - 2012)
  > - **COMPoissonReg** (Kimberly Sellers e Thomas Lotze - 2011)

---

<img src="/home/eduardojr/Dropbox/Graduação/FinalWork/Preliminary/Siepe2015/Seminarios_Discentes/Slide/assets/img/slidify_logo_big.png" align="middle" height="300" width="400" margin="0 auto" />

<font size="50"><b>
<div style='text-align: center;'>Obrigado!</div>
</b></font>
