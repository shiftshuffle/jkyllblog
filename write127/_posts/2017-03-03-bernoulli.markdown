---
layout: post
title:  "Bernoulli Numbers"
date:   2017-03-03 09:11:03
description: Bernoulli numbers.
thumbnail: building1.jpg
categories: [math,analytic,combinatoric]
comments: true
# Information for the author block
author: Shift Shuffle
---

Bernoulli numbers are defined as de coefficients  $B(n) $ when expanding

$$   \frac{ x }{  e^{x} - 1 } = \displaystyle{\sum_{n=0}^{\infty}  B_{n} \frac{  x^{n}  }{ n! }}  $$

we have the following relation:

$$ - e^{x} + x +1 =  \displaystyle{  \left(\! \sum_{n=1}^{\infty} B_{n} \frac{  x^{n}  }{ n! }    \!\right)   \left(\!  \sum_{k=1}^{\infty}  \frac{  x^{k}  }{ k! }   \!\right)}   $$



$$   \ \    $$
$$   \ \    $$

$$ \Longrightarrow   $$

$$   \ \    $$
$$   \ \    $$


$$ -   \sum_{j=2}^{\infty}  \frac{  x^{j}  }{ j! }  =  \sum_{k=2}^{\infty}  \frac{  x^{k} }{ k! }  \sum_{l=1}^{k-1}  \left(\!  \begin{array}{c}  k \\  l  \end{array}  \!\right)  B_{l} \qquad (1)$$






$$   \ \    $$
$$   \ \    $$

Remember Cauchy Convolution :

$$   \displaystyle{  \left(\! \sum_{i=0}^{\infty} a_{i}  x^{i}     \!\right)   \left(\! \sum_{j=0}^{\infty}  b_{j}  x^{j}    \!\right) =  \sum_{k=0}^{\infty} c_{k}  x^{k}}  $$


Where

$$   c_{k} = \sum_{l=0}^{k} a_{l}  b_{k-l}   $$

$$   \ \    $$
$$   \ \    $$


if we apply it here  $$  \displaystyle{  \left(\! \sum_{n=1}^{\infty} B_{n} \frac{  x^{n} }{ n! }    \!\right)   \left(\!  \sum_{k=1}^{\infty}  \frac{  x^{k}  }{ k! }   \!\right) = \sum_{k=2}^{\infty} c_{k}  x^{k}} $$

and


$$   c_{k} = \sum_{l=1}^{k-1}\begin{eqnarray} \frac{ B_{l} }{ l! ( k - l )! } \end{eqnarray}  =  \frac{  1  }{ k! }  \sum_{l=1}^{k-1}  \left(\! \begin{array}{c} k \\ l  \end{array} \!\right)  B_{l} $$

$$   \ \    $$
$$   \ \    $$

now that we have derived $\qquad (1)$  we equate coefficients and get
$$  \sum_{l=1}^{k-1}  \left(\!  \begin{array}{c}  k \\  l  \end{array}  \!\right)  B_{l} = -1  $$

$$   \ \    $$
$$   \ \    $$

$$  \sum_{l=1}^{k-1}  \left(\!  \begin{array}{c}    k \\ l  \end{array}  \!\right)  B_{l} = - \left(\!  \begin{array}{c}  k \\  0  \end{array}  \!\right) B_{0}$$

taking in account $ B_{0}=1    $

We get
$$   \ \    $$
$$   \ \    $$

$$   \begin{eqnarray} \sum_{l=0}^{k-1}  \left(\!  \begin{array}{c}  k \\  l  \end{array}   \!\right)  B_{l} = \begin{cases} 1& ,  k= 1  \\ 0 & ,  k \geqq 2 \end{cases} \end{eqnarray} $$
