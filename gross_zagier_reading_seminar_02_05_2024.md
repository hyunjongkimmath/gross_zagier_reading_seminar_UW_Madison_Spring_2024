---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# Regularized theta lifting + theta CM values

Speaker: [[yang_tonghai]]

Lots of people have different ways to find problems to work on. For this paper, the initial goal was not the Gross-Zagier formula at all. It was to try to understand Schofer's thesis and whether one can use it to generalize/understand the Bruinier-Yang 2006 paper


Schofer's thesis was very nice, and then Bruinier proposed to Yang "let's try solving an easier problem".

Let $\Phi(z,h,f) = \int f(\tau) \theta_L (\theta, z, h) d\mu(\tau)$

Here, $(z,h)$ live in a Shimura variety written $X$, and $\tau$ lives in the upper half plane $\tau$. The integral is over a fundamental domain of $\operatorname{SL}_2(\mathbb{Z}) \backslash \mathbb{H}$. Moreover, $f : \mathbb{H} \to \mathbb{C}$ is a weakly holomorphic modular form. For example, $j(z) = q^{-1} + \cdots$. However, a weakly holomorphic modular form blows up at $\tau = \infty$, so you need to regularize the integral


$\Phi(z,h,f) = \int^{\text{reg}} f(\tau) \theta_L (\theta, z, h) d\mu(\tau)$

We have $\Phi(\text{CM}(E), f) = \sum_{(z,h) \in \operatorname{CM}(E)}  \Phi(Z,h,f)$; here, $\operatorname{CM}(E)$ is a finite set in $X$.

> [!Theorem]
> Schofer's theorem
> $\Phi(\text{CM}(z), f) = \sum_{p \text{ prime}, p < \infty, p < d(Z)} a_p \log p$

Consider the special case[^2] $f = j(\tau) - 744$ and $X = Y(1) \times Y(1) = \operatorname{Sl}(\mathbb{Z}) \backslash \mathbb{H} \times \operatorname{Sl}(\mathbb{Z}) \backslash \mathbb{H}$. Here,

$$\Phi(z_1, z_2, f) = -\log |j(z_1) - j(z_2)|^2$$

Write $E = \mathbb{Q}(\sqrt{d_1}, \sqrt{d_2})$. Then $\Phi(\operatorname{CM}(E), j-744) = \sum_{\operatorname{disc}(\tau_1) = d_1, \operatorname{disc}(\tau_2) = d_2} - \log|j(\tau_1) - j(\tau_2)|^2$ By Gross Zagier, this then equals $\sum_{p \leq d_1d_2} a_p \log p$

[^2]: Apparently, Schofer's theorem doesn't actually apply to this case.


We have an exact sequence

$$0 \to M_{2-k}^! \hookrightarrow H_{2-k} \xrightarrow{\xi} S_k$$

$M_{2-k}^!$ is the space of weakly holomorphic forms,  $H_{2-k}$ is the space of Harmonic Maass forms, and $S_k$ is the space of holomorphic cuspidal forms of weight $k$.


The work of Bruinier-Yang tries out the following ideas:

1. $f \in M_{2-k}$: do the same calculation (First four sections of the paper; Theorem 4.6 is the main theorem)
- The analogue of Schofer's theorem: $\Phi(\text{CM}(E), f) = \sum_{p < \infty} a_p \log p + L'(\xi(f), \theta, \text{Center})$

$\xi(f)$ is the Rankin-Selbert $L$-function

2. Conjecture: let $\hat{Z}(f) = (Z(f), \Phi(f)) \in \widehat{\operatorname{CH}}^1(\mathscr{X})$. Then $\langle \hat{Z}(f), \operatorname{CM}(z) \rangle_{\text{Fal}} = L'(\xi(f), \theta, \text{center})$ verify low dimension case. The conjecture was eventually proven in 2015 by Bruinier-Howard-Yang

3. Surprise: give a proof of a variant of Gross-Zagier formula without doing any finite intersection!!

modularity: $\sum \hat{Z}(m)q^m$ modular (Bruinier-Howard-Kudla-Rapoport-Yang, circa 2020)
- Other CM values (2013) (Bruinier-Kudla-Yang)

# Outline of paper

I: Weil representation, theta lifting, theta kernel

II: Shimura variety of orthogonal type $O(n,2)$ ($\operatorname{GSpin(V)} \to \operatorname{SO}(V)$) and Siegel-Weil formula
- Special divisors
- Small CM cycles

III: The main formula (quite simple / Soft)


# 

Let $(V,Q)$ be a quadratic space of sign $(n,2)$. Write $m = n+2$.

Let $H = \operatorname{SO}(V) = \{ h \in \operatorname{End}(V) : (hx, hy) = (x,y) \text{ for all } x,y \in V, \det h = 1 \}$. Let $G = \operatorname{SP}_2 = \operatorname{SP}(W) = \operatorname{SL}_2$. We have a map

$$G \times H \to \operatorname{Sp}(V \otimes_\mathbb{Q} W)$$

that we can also take adelically (over $\mathbb{A}$). We have  a map $\operatorname{Mp}(V \otimes_\mathbb{Q} W) / \mathbb{A} \to \operatorname{Sp}(V \otimes_\mathbb{Q} W) / \mathbb{A}$. We also have $\omega = \omega_\psi$ on $S(V_\mathbb{A}) = \otimes'_{p \leq \infty} S(V_p)$. 

Let $\psi: \mathbb{A} \to \mathbb{C}^1$ be an additive character.

$\omega_{V,\psi}$ is a representation of $G/\mathbb{A} \times H_\mathbb{A}$ on $S(\mathbb{A})$ given by

$$\omega_{V,4} (h) \varphi(x) = \varphi(h^{-1} x)$$

We also have formulae

$$\omega_{V, \psi}(n(b)) \varphi(x) = \psi(Q(x)) \varphi(x)$$
$$\omega_{V, \psi}(m(b)) \varphi(x) = \chi(a) |a|^{\frac{m}{2}}_\mathbb{A}  \varphi(x \cdot a)$$
$$\omega_{V, \psi}(w) \varphi(x) = \gamma(v_\mathbb{A}) \int_{V_\mathbb{A}} \varphi(y) \psi(-(x,y)) dy$$

where $n(b) = \begin{pmatrix} 1 & b\\ 0 & 1 \end{pmatrix}$, $m(a) = \begin{pmatrix} a & 0 \\ 0 & a^{-1} \end{pmatrix}$, $w = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$, $\chi(a)$ isa quadratic character, and $\gamma(V_\mathbb{A})$ is roots of unity.

## Theta kernel


For $\varphi \in S(V_\mathbb{A})$, define

$$\Theta(g,h,\varphi) = \sum_{x \in V} \omega(g) \varphi(h^{-1} x)$$

for $g \in G(\mathbb{A})$ and $h \in H(\mathbb{A})$. This converges and is $G(\mathbb{Q}) \times H(\mathbb{Q})$-invertible, i.e. it is a modular form on $[G] \times [H]$. Here, $[G]$ 


If $f$ is a modular form on $[G]$, then  $G(\mathbb{Q}) \backslash G(\mathbb{A}) \subset [G]$.

$$\Theta(h,f) = \int_{[G]} f(g) \Theta(g,h,\varphi) dg$$

is a modular form on $[H]$. Then you get that

$$\int_{[H]} f(h) \Theta(g,h) dh$$


is a modular form on $[G]$. We will modify $\Theta(h,f)$.


# Siegel-Weil formula

The Siegel-Weil formula is the theta liting. 

Let $f = 1$ on $[H]$. Then you get 

$$\Theta(g,\varphi) = \int_{[H]} \Theta(g,h,\varphi) dh \cdot \frac{1}{\operatorname{vol}([H])} = ?$$ 

What is this equal to? It turns out to be equal to an Eisenstein series by the Siegel-Weil formula:

$$ = E(g, S_0, \varphi)$$

where $S_0  = \frac{\dim V - 2}{2}$.


Siegel did things where $(V,Q)$ is a quadratic space of sign $(n,0)$ instead, and then $\Theta(g,h,\varphi)$ apparently becomes a counting function (of numbers of ways to express integers are sums of squares).

# Shimura variety

Given $(V,Q)$, we get $H = \operatorname{SO}(V)$. Let $\mathbb{D} = \{ \text{oriented negative } 2\text{-planes in } V_\mathbb{R} \} = \{ Z \subset V | \dim Z = 2, Q|_Z > 0 \}$.

Let $K \subset H(\mathbb{A}_f)$ be compact open. Then we can produce a Shimura variety $X_K/\mathbb{Q}$ such that  $X_K(\mathbb{C}) = H(\mathbb{Q}) \backslash \mathbb{D} \times H(\mathbb{A}_f) / K = \coprod \Gamma_j \backslash \mathbb{D}$. 

Shimura actually studied $\Gamma_j \backslash \mathbb{D}$ and then Deligne came along to study Shimura varieties as we talk about them today.

For 
- $(0,2)$,
	- we have CM points,
- $(1,2)$
	- we have Shimura curves,
- $(2,2)$,
	- we have products of Shimura curves and Hilbert modular surfaces.
- $(3,2)$
	- We have Siegel $3$-folds and probably other things


Given a lattice $L \subset V$, let

$$Z(m,L) "=" \Gamma \backslash \{z \in \mathbb{D}: \exists x \in L \text{ with } Q(x) = m, x \perp z\}.$$

This is of codimension $1$.

## Small CM cycle

Take $U \subset V$ a negative $2$ subspace. Then $U_\mathbb{R}^{\pm} \in \mathbb{D}$. We call $z^{\pm}$ the points given by $U_\mathbb{R}$. 

Also, $H_U = \operatorname{SO}(U) = k^1$ where $k = \mathbb{Q}(\sqrt{-\det U})$. Here,

$$Z(U) = \{Z_u^\pm \} \times k^1 \backslash k_f^1 / K_U = \text{small CM cycles defined over } \mathbb{Q}$$

# Main result

Let $L \subset V$ be unimodular. We have a $\Theta$ function

$$\Theta(g,h, \varphi) $$ 

where $g \in \operatorname{SL}_2(\mathbb{A}) = \operatorname{SL}_2(\mathbb{Q}) \operatorname{SL}_2(\hat{\mathbb{Z}}) \operatorname{SL}_2(\mathbb{R})$. Also, $\operatorname{SL}_2(\mathbb{R})$ is $B \cdot \operatorname{SO}(2)$ where $B$ consists of real matrices of the form $\begin{pmatrix} a & b \\ 0 & a^{-1} \end{pmatrix}$. 

Write $\tau = u+iv \in \mathbb{H}$, and $g_\tau = \begin{pmatrix} 1 & u \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \sqrt{u} & 0 \\ 0 & \frac{1}{\sqrt{u}} \end{pmatrix}$.

Also, $h \in \operatorname{SO}(V) (\mathbb{A})$

...

For $z \in \mathbb{D}$, $z \subset V_\mathbb{R}$. Decompose $V_\mathbb{R} = z \oplus z^\perp$, so given $x \in V_\mathbb{R}$, write it as $x = x_z + x_{z^\perp}$. We have 

$$\varphi_\infty(z,x) = e^{- \pi((x_{z^\perp}, x_{z^\perp}) - (x_z, x_z))}$$

Then we have

$$\Theta(\tau, z, h, \varphi_f, \varphi_\infty) = \sum_{x \in V} \omega(g_z) \varphi_\infty (x) \varphi_f(h^{-1} x)$$

This is a modular form on $\tau$ of weight $\frac{n-2}{2}$

$f: \mathbb{H} \to \mathbb{C}$ weight $\frac{2-n}{2}$ Harmonoic Maass modular form.

$$\Phi(z,h,f) = \int_{\text{fundamental domain}}^{\text{reg}} f(z) \Theta(\tau, z, h) d\mu(\tau)$$

This $\Theta_{\text{reg}}$ function is a Green function of $Z(f) = \sum C_f(-m) Z(m,L)$ by the thesis of Bruinier, and by Bruinier-Funke


> [!Theorem]
> (Bruinier-Yang 2009)
> $\Phi(Z(U), f) = \sum_p a_p \log p + L'(\xi(f), \theta_P, \text{center})$

where $V = U \oplus P$ where $U$ and $P$ are the $(0,2)$ and $(n,0)$ parts of $V$ and $L \supset L_U \oplus J_\Gamma$...

Proof: ...
















# See Also

# Meta
## References

## Citations and Footnotes