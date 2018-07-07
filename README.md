# Potts Model
This repository was built with the objective of studying the effects of dopage in the family of compounds <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{120}&space;\mathrm{CeCo}_{1-x}\mathrm{Fe}_{x}\mathrm{Si}^{}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{120}&space;\mathrm{CeCo}_{1-x}\mathrm{Fe}_{x}\mathrm{Si}^{}" title="\mathrm{CeCo}_{1-x}\mathrm{Fe}_{x}\mathrm{Si}^{}" /></a>
##  Random Number Generators

#### Tausworthe Generators 
Tausworthe Generator (TG) is a kind of multiplicative recursive generator which produces random bits. It has the following form:

<a href="https://www.codecogs.com/eqnedit.php?latex=x_{n&plus;1}&space;=&space;(A_{1}x_{n}&space;&plus;&space;A_{2}x_{n-1}&space;&plus;&space;\cdots&space;&plus;&space;A_{k}x_{n-k&plus;1})\mod{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{n&plus;1}&space;=&space;(A_{1}x_{n}&space;&plus;&space;A_{2}x_{n-1}&space;&plus;&space;\cdots&space;&plus;&space;A_{k}x_{n-k&plus;1})\mod{2}" title="x_{n+1} = (A_{1}x_{n} + A_{2}x_{n-1} + \cdots + A_{k}x_{n-k+1})\mod{2}" /></a>

where <img src="https://latex.codecogs.com/gif.latex?\inline&space;x_{i},&space;A_{i}\in&space;\left&space;\{&space;0,1&space;\right&space;\}\hspace{0.2cm}\forall&space;i" title="x_{i}, A_{i}\in \left \{ 0,1 \right \}\hspace{0.2cm}\forall i" />

The theory behind TG is related to irreducible primitive polynomials over GF(2). A polynomial over Galois field of order 2 (GF(2)) is a polynomial whose coefficients are either 0 and 1. Such a polynomial is irreducible primitive if it does not have nontrivial factors like 1 and has order of <img src="https://latex.codecogs.com/gif.latex?\inline&space;2^{n}-1" title="2^{n}-1" /> for some <img src="https://latex.codecogs.com/gif.latex?\inline&space;n" title="n" />. The order of a polynomial <img src="https://latex.codecogs.com/gif.latex?\inline&space;f(x)" title="f(x)" /> over GF(2) is the smallest integer <img src="https://latex.codecogs.com/gif.latex?\inline&space;e" title="e" />  for which <img src="https://latex.codecogs.com/gif.latex?\inline&space;f(x)" title="f(x)" /> divides <img src="https://latex.codecogs.com/gif.latex?\inline&space;x^{e}-1" title="x^{e}-1" />. For example <img src="https://latex.codecogs.com/gif.latex?\inline&space;x^{2}&plus;x&plus;1" title="x^{2}+x+1" />  is irreducible primitive with order <img src="https://latex.codecogs.com/gif.latex?\inline&space;3&space;=&space;2^2&space;-&space;1" title="3 = 2^2 - 1" />, while <img src="https://latex.codecogs.com/gif.latex?\inline&space;x^2&plus;1=\left&space;(&space;x&plus;1&space;\right&space;)^2" title="x^2+1=\left ( x+1 \right )^2" /> is not even irreducible.

When the characteristic polynomial of the above form <img src="https://latex.codecogs.com/gif.latex?\inline&space;P\left&space;(&space;z&space;\right&space;)&space;=&space;z^{k}&space;-&space;A_{1}z^{k-1}&space;-&space;\cdots&space;-&space;A_{k}" title="P\left ( z \right ) = z^{k} - A_{1}z^{k-1} - \cdots - A_{k}" /> s an irreducible primitive and the $k$ initial seeds are not all zero, the corresponding TG will have a period of <img src="https://latex.codecogs.com/gif.latex?\inline&space;2^{k}-1" title="2^{k}-1" /> . To obtain random numbers instead of bits, we can output the decimal values of every <img src="https://latex.codecogs.com/gif.latex?\inline&space;k" title="k" />-consecutive bits. 

Since TG only produces bits, it is too slow to be useful. A technique to speed up is to use a special form called trinomial-based TG. A trinomial is a polynomial with only three coefficients being nonzero, so a trinomial-based TG has only two of the <img src="https://latex.codecogs.com/gif.latex?\inline&space;A_{i}" title="A_{i}" /> coefficients of the characteristic polynomial being nonzero. This results in a very fast, hardware-based implementation technique called Feedback Shift Register (FSR) which involves shift, AND, and XOR operations on a small set of img src="https://latex.codecogs.com/gif.latex?\inline&space;k" title="k" />
