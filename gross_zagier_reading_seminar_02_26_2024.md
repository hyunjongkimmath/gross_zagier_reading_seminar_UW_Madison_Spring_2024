---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# Eisenstein series
Speaker: [[luo_yu]]

The Siegel-Weil formula is pretty concrete. The following is some related exposition.

Consider the sum of squares problem. For instance, $5$, $13$, $17$, and $29$ are all expressible as sums of two integers squares. However, $3,7,11,19,23$ are not.

Also, note that

$$(a^2+b^2)(c^2+d^2) = (ac-bd)^2 + (ad+bc)^2$$


> [!Theorem]
> For $n > 0$, $n = x^2+y^2$ for some integers $x,y$ if and only if prime divisor $p \equiv 3 \pmod{4}$ of $n$ has even degree.


Write $r(n) = \# \{(x,y) \in \mathbb{Z}^2: n = x^2+y^2\}$

> [!Theorem]
> (Jacobi)
> $r(n) = 4 \left( \sum_{\substack{d \mid n \\ d \equiv 1 \pmod{4}}} 1 - \sum_{\substack{d \mid n \\ d \equiv 3 \pmod{4}}} 1 \right)$

For instance, if $p \equiv 1 \pmod{4}$, then $r(p) = 8$ and if $p \equiv 3 \pmod{4}$, then $r(p) = 0$. 


Now define the <b style="border-width:1px;border-style:solid;padding:3px" definition="">Jacobi theta function</b>

$$\theta(q) = \sum_{n \in \mathbb{Z} q^{n^2}} = 1 + 2q + 2q^4 + \cdots + 2q^{n^2} + \cdots$$

Then 

$$\theta^2(q) = \sum_{n \in \mathbb{N}} \tau(n) q^n = 1 + 4q + \cdots $$

It turns out that $\theta^2(q) \in \mathcal{M}_1(\Gamma_1(4))$.

Now a very concrete fact about $\mathcal{M}_1(\Gamma_1(4))$ is that is it $1$-dimensional.

There is a way to concretely construct the modular forms of any weight: with the Eisenstein series.

Let $\chi: (\mathbb{Z}/4\mathbb{Z})^\times \to \mathbb{C}^\times$ be the nontrivial character.

Then let

$$E_k^\chi(\tau) = \sum_{\Gamma_\infty \backslash \Gamma_1(4)} \frac{\chi(d)}{(c\tau+d)^k}$$

where $\Gamma_\infty = \begin{pmatrix} 1 &  * \\ 0 & 1 \end{pmatrix}$. When $k = 1$, while this may not be absolutely convergent, we still have $E_1^\chi(\tau) \in \mathcal{M}_1(\Gamma_1(4))$.

We have a Fourier expansion

$$E_k^\chi(\tau) = 1 + c_k^\chi \sum_{n \geq 1} \left( \sum_{d \mid n} \chi(d) d^{k-1} \right) q^n$$

Since $\mathcal{M}_1(\Gamma_1(4)) = 1$, $\theta^2(q)$ and $E_1^\chi(\tau)$ are equal up to a scalar. By comparing the Fourier coefficients of both modular forms, we have

$$4 = C^\chi_1$$

$$\tau(n) = 4 \left( \sum_{d \mid n} \chi(d) \right)$$

and thus Jacobi's theorem above follows.


# $\theta$-function

Let $V$ be a vector space over $\mathbb{Q}$ with quadratic form $Q: V \to \mathbb{Q}$. Write $H$ for the Heisenberg group. Fix an additive character $\psi: \mathbb{A} \to \mathbb{C}^\times$. Recall that there is a character $\psi_\infty e^{2\pi i x}$. Let $H$ be the Heisenberg group. There is an action of $G(\mathbb{A}) \times H(\mathbb{A})$ on $S(V(\mathbb{A}))$.

Let $\varphi \in S(V(\mathbb{A}))$. Write

$$\theta(g,h;\varphi) = \sum_{x \in V(\mathbb{Q})} \omega(g) \varphi(h^{-1} x)$$


Define the $\theta$-integral

$$\int_{H(\mathbb{Q}) \backslash H(\mathbb{A})} \theta(g,h;\varphi) dh$$

$V$ is a positive definite quadratic form space. Let $\Lambda \subset V$ be a lattice.
Let $\varphi_p  = \operatorname{char}(\Lambda \otimes \mathbb{Z}_p)$ and $\varphi_\infty(x) = e^{- 2 \pi \mathbb{Q}[x]}$. Let $K \subset H(\mathbb{A})$ denote the stabilizer of $\Lambda$. Recall that there is a natural identfication

$$H(\mathbb{Q}) \backslash H(\mathbb{A}) / K \xrightarrow{\sim} \operatorname{Gen}(\Lambda)$$

where $\operatorname{Gen}(\Lambda)$ is the set of isomorphism classes of lattices with the same genus as $\Lambda$. The identification sends $h \in H(\mathbb{Q}) \backslash H(\mathbb{A}) / K$ to $h(\Lambda \otimes \hat{\mathbb{Z}}) \cap V$

Classically, it is known that $\operatorname{Gen}(\Lambda)$ is finite. Write $\{h_i\}$ for representatives of $H(\mathbb{Q}) \backslash H(\mathbb{A}) / K$ and $\{\Lambda_i\}$ for representatives of $\operatorname{Gen}(\Lambda)$


> Later on, we will use an example of $V = \mathbb{Q}^2$ where the quadratic form $Q$ is given by $Q = x^2+y^2$ where $(x,y) \in V$.

Now we have

$$\begin{align*}
\int_{H(\mathbb{Q}) \backslash H(\mathbb{A})} \theta dh &= \sum_i \int_{H(\mathbb{Q}) \backslash H(\mathbb{Q}) / h_i K} \theta(g,h;\varphi) dh \\
&= \sum_i \int_{H(\mathbb{Q}) \backslash H(\mathbb{Q}) h_i K h_i^{-1}} \theta(g, hh_i; \varphi) dh.
\end{align*}$$

We also have

$$H(\mathbb{Q}) \backslash H(\mathbb{Q}) h_i K h_i^{-1} \simeq (H(\mathbb{Q}) \cap h_i Kh_i^{-1}) \backslash h_i K h_i^{-1}$$

Also, $(H(\mathbb{Q}) \cap h_i Kh_i^{-1}) = \operatorname{Aut}(\Lambda_i)$

Now the summand

$$\int_{H(\mathbb{Q}) \backslash H(\mathbb{Q}) h_i K h_i^{-1}} \theta(g, hh_i; \varphi) dh$$

from before equals

$$\begin{align*}
&= \frac{1}{\# \operatorname{Aut}(\Lambda_i)} \int_{h_i K h_i^{-1}} \theta(g,hh_i, \varphi) dh \\
&= \frac{1}{\#\operatorname{Aut}(\Lambda_i)} \int_K \theta(g, h_ih; \varphi) dh
\end{align*}$$

By strong approximation, write

$$g = g_i = \begin{pmatrix} 1 & u \\ 0 & 1 \end{pmatrix} \begin{pmatrix} v^{\frac{1}{2}} & 0 \\ 0 & v^{-\frac{1}{2}} \end{pmatrix}$$

where $\tau = u + iv$.

Continuing on, we have

$$\int_K \theta(g_\tau, h_i h; \varphi) dh = \sum_K \sum_{x \in V(\mathbb{Q})} \omega(g_\tau) \varphi(h^{-1} h_i^{-1} x) dh$$

Now $h^{-1} h_i^{-1} x$ is in $\Lambda \otimes \mathbb{Z}_p$ if and only if $x \in h_i h \Lambda \otimes \mathbb{Z}_p = \Lambda_i \otimes \mathbb{Z}_p$. Thus, the above equals

$$\begin{align*}
&\int_K \sum_{x \in \Lambda_i} \omega_\infty (g_i) \varphi_\infty(x) dh \\
&= \operatorname{vol}(K) \sum_{x \in \Lambda_i} \omega_\infty(g_i) \varphi_\infty(x).
\end{align*}$$

The summand $\omega_\infty(g_i) \varphi_\infty(x)$ equals

$$\begin{align*}
\omega_\infty ( n(u) m(v^{\frac{1}{2}})) \varphi_\infty(x) &= \psi(uQ(x)) |v|^{\frac{m}{4}} \varphi_\infty(x v^{\frac{1}{2}} ) \\
&= |v|^{\frac{m}{4}} e^{2 \pi i uQ(x)} \cdot e^{2 \pi v} Q(x)
&=  |v|^{\frac{m}{4}} e^{2 \pi i \tau Q(x)}
\end{align*}$$

where $m = \dim V$, so going back, we have

$$\operatorname{vol}(K) |v|^{\frac{m}{4}} \sum_{x \in \Lambda_i} e^{2 \pi i \tau Q(x)}.$$


## Example 1
Now let us take the example of $V = \mathbb{Q}^2$, $\mathbb{Z}^2 \subset V$, and $Q[(x,y)] = x^2+y^2$.

We have the square of the theta function

$$\sum_{a,b \in \mathbb{Z}^2} q^{a^2 + b^2} = \Theta^2(q)$$

## Example 2
When we have $V = \mathbb{Q}$, $Z \subset V$, and $Q[x] = x^2$, we have the $\theta$ function

$$\sum_{n \in \mathbb{Z}} q^{n^2} = \theta(q)$$

## Summary

So the work that was done in this section shows that Theta integral is closely related to the sum $\sum_{x \in \Lambda_i} e^{2\pi i \tau Q(x)}$, which specializes in the two examples above to $\theta^2(q)$ and $\theta(q)$


# Eisenstein series 

> [!Definition]
> $I(s, \chi) = \operatorname{Ind}^{G(\mathbb{A})}_{B(\mathbb{A})} \chi_V | \cdot |^{s+1}$
> where $B(\mathbb{A})$ is the Borel group

There is a principal series representation $\Theta(g,s)$. We have

$$\Theta(n(b) m(a) g, x) = \chi(a) |a|^{s+1|} \Phi(g)$$

[^1]

[^1]: $m(a)$ denotes $\begin{pmatrix} a & 0 \\ 0 & a^{-1} \end{pmatrix}$ and $n(b)$ denotes $\begin{pmatrix} 1 & b \\ 0 & 1 \end{pmatrix}$ and $w = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}$


## Example

There is a map $\lambda: S(V(\mathbb{A})) \to I(s_0, \chi_v)$ sending $\varphi$ to $\lambda(\varphi)$ where $\lambda(\varphi)(g) = (\omega(g) \varphi)(0)$.

Let us  check that the conditions of $\lambda(\varphi)$ to be in the induced representation are satisfied:

$$\lambda9\varphi)(n(b) m(a) g, s_0) = \omega(n(b) m(a) g) \varphi(0) = \chi_v(a) |a|^{s_0 + 1} \omega(g) \varphi(0).$$


Here, $\lambda(\varphi)(g)$ is $\omega(g)$???

## Back to the discussion

A section $\Phi(s)$ is called <b style="border-width:1px;border-style:solid;padding:3px" definition="">standard</b> if $\Phi(s) |_{K_\infty K}$ is constant.


We define the <b style="border-width:1px;border-style:solid;padding:3px" definition="">Eisenstein series</b>

<span style="border-width:1px;border-style:solid;padding:3px" notation="">$$E(g,s;\Phi) = \sum-{\gamma \in B(\mathbb{Q}) \backslash G(\mathbb{Q})} \Phi(\gamma g, s)$$</span>

In the case that $\Phi = \lambda(\varphi)$, we have a Siegel Eisenstein series.

Now we are not assuming that $V$ is a positive definite quadratic space.

> [!Theorem]
> (Siegel-Weil formula)
> $$\frac{\alpha}{2} \int_{O(\mathbb{Q}) \backslash O(\mathbb{A})} \theta(g,h;\varphi) dh = E(g, s_0; \lambda(\varphi))$$


## Simon's comments on the local theta correspondence

Let $F$ be a $p$-adic local field. Let $\psi$ be an additive character on $F$. Let $W$ be a symplectic space. Let $V$ be an even orthogonal space. Let $\mathbb{W} = W \otimes V$. Let $G = \operatorname{Sp}(W)$. Let $H = O(V)$. Let $\omega$ be the Weil representation of $\tilde{S}_p(\mathbb{W})$.


We say that $\pi_G \in \operatorname{Irr}(G)$ and $\pi_H \in \operatorname{Irr}(H)$ correspond if $\operatorname{Hom}_{G \times H}(\omega, \pi_G \otimes \pi_H) \neq 0$.


> [!Theorem]
> (Moeglin-Vigneras-Waldspurger for $p >2$; $p = 2$ is really hard and has only been done more recently, Howe for $f = \mathbb{R}$)
> This correspondence is a bijection is a bijection between a subset of $\operatorname{Irr}(G)$ and $\operatorname{Irr}(H)$

"A representation occurs in the Theta correspondence if it is a quotient of $\omega$. The local theta correspondence is a partial bijection between two sets of representations"

The correspondence is "1. take $\pi_G$. 2. Look for representation $\pi_H$ such that $\pi_G$ and $\pi_H$ correspond (i.e. such that $\operatorname{Hom}_{G \times H}( \omega, \pi_G \otimes \pi_H)) \neq 0$". And then this is apparently a bijection for some subset of $\operatorname{Irr}(G)$ and $\operatorname{Irr}(H)$

Write $\omega[\pi_G]$ for the maximal quotient of $\omega$ for which $G$ acts $\pi_G$-isotypically.

Then $\omega[\pi_G] \simeq \pi_G \otimes \Theta(\pi_a)$.

> [!Theorem]
> $\Theta(\pi_G)$ has a unique irreducible quotient as a representation of $H$. The quotient is $\Theta(\pi_G)$


## Simon's comments on the global theta correspondence

We have an integral

$$\theta(g, \phi, \varphi) = \int_{[H]} \Theta(g,h,\varphi) \overline{\phi}(h) dh$$

One of the important things about this map is that the integral is $H$-invariant: $\int_{[H]} \Theta(g,h,h'\varphi) h'\overline{\phi}(h) dh$

What this integral is doing is that it is giving an element of $\operatorname{Hom}_{(G \times H)(\mathbb{A})}(\omega \otimes \pi_H^\vee, \mathcal{A}(G))$ -- in particular, said element is equivariant for the $(G \times H)(\mathbb{A})$ actions. Also, this Hom space is isomorphic to $\operatorname{Hom}_{(G \times H)(\mathbb{A})}(\omega, \pi_H \otimes \mathcal{A}(G))$.

The image of the integral, which is in $\mathcal{A}(G)$, is apparently a quotient of $\Theta(\pi_H)$ by the local theta correspondence.


# How to relate Eisenstein series with classical Eisenstein series

Let $\chi$ be the trivial character. Take $\ell$ to be an even number. Write $k_\theta = \begin{pmatrix} \cos \theta & \sin \theta \\ -\sin \theta & \cos \theta \end{pmatrix} \in K_\infty = \operatorname{SO}(2)$. Pick a function $\Phi_\infty^\ell$ so that

$$\Phi_\infty^\ell (g k_\theta) = e^{2 \pi i \ell \theta} \Phi_\infty^\ell(g)$$

Writing $\tau = u+iv$, it suffices to understand the values at $g_\tau = \begin{pmatrix} 1 & u \\ 0 & 1 \end{pmatrix} \begin{pmatrix} u^{\frac{1}{2}} & 0 \\ 0 & v^{-\frac{1}{2}} \end{pmatrix}$ (by something about strong approximation?).

Write $\Phi = \Phi_\infty^\ell \otimes \Phi_p$.

Also let 
$$E(g_\tau, s, \Phi) = \sum{\gamma \in B(\mathbb{Q} \backslash G(\mathbb{Q})} \Phi(\gamma g_{\tau} s)$$


We have
$B(\mathbb{Q}) \backslash G(\mathbb{Q}) \simeq \Gamma_\infty \backslash \operatorname{SL}_2(\mathbb{Z}) \simeq \mathbb{P}^1(\mathbb{Q}) \simeq \mathbb{P}^1(\mathbb{Z})$


> [!Lemma]
> For $\gamma = \begin{pmatrix} a & b \\ \cdot & d \end{pmatrix} \in \operatorname{SL}_2(\mathbb{Q})$,
> Write $\gamma g_\tau = g_{\gamma \tau} \cdot k_\theta$ where $k_\theta$ lies in the upper half plane. Then
> $$e^{i \theta} = \frac{c \overline{\tau} + d}{| c \tau + d |}.$$

> [!Lemma]
> $\operatorname{Im}(\gamma\tau) = \frac{\operatorname{Im}(\tau)}{|c\tau + d|^2}$

> [!Lemma]
> $\Phi_\infty^\ell (g_\tau, s) = \Phi_\infty^\ell \left( \begin{pmatrix} 1 & u \\ 0 & 1 \end{pmatrix} \begin{pmatrix} v^{\frac{1}{2}} & 0 \\ 0 & v^{-\frac{1}{2}} \end{pmatrix},s \right) = |v|^{\frac{1}{2}(s+1)}$

...

You do a bunch of stuff and recover the original Eisenstein series with $\ell = 1$.









# See Also

# Meta
## References

## Citations and Footnotes