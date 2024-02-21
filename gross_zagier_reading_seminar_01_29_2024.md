---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# 

Speaker: [[luo_yu]]

We will be interested in $O(0,2)$, $O(1,2)$, and $O(2,2)$.

$O(0,2)$ correspond to algebraic points, $O(1,2)$ corresponds to modular curves, and $O(2,2)$ corresponds to modular surfaces.

We need to understand automorphic forms


# 1. Review of modular forms

> [!Definition]
> (Congruence subgroup) $\Gamma \subset \operatorname{SL}_2(\mathbb{Z})$ is a congruence subgroup if it contains some principal congruence subgroup $\Gamma(N) := \ker \operatorname{SL}_2(\mathbb{Z}) \to \operatorname{SL}_2(\mathbb{Z}/N\mathbb{Z})$.

Examples:

$$\Gamma_1(N) = \left\{ \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in \operatorname{SL}_2(\mathbb{Z}) : \equiv \begin{pmatrix} 1 & * \\ 0 & 1 \end{pmatrix} \pmod{N} \right\}$$

$$\Gamma_0(N) = \left\{ \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in \operatorname{SL}_2(\mathbb{Z}) : \equiv \begin{pmatrix} * & * \\ 0 & * \end{pmatrix} \pmod{N} \right\}$$

> [!Definition]
> 1. $\mathbb{H} = \{\tau \in \mathbb{C} : \operatorname{im}(\tau) > 0 \}$
> 2. $\operatorname{SL}_2(\mathbb{Z})$ acts on $\mathbb{H}$ by $\tau \mapsto \frac{a\tau + b}{c \tau + d}$
> 3. $Y(\Gamma) \cong \Gamma \backslash \mathbb{H}$, $Y_0(N) = Y(\Gamma_0(N)), Y_1(N) = Y(\Gamma_1(N))$
> 4. $X(\Gamma) = \Gamma \backslash \mathbb{H} \cup \mathbb{P}^1(\mathbb{Q})$

Examples: 
1. $\operatorname{SL}_2(\mathbb{Z}) \backslash \mathbb{H} \xrightarrow{j} \mathbb{A}^1; \tau \mapsto \mathbb{C}/(\mathbb{Z} + \tau \mathbb{Z}) \mapsto j(E_\tau)$
2. $\Gamma(2) \backslash \mathbb{H} \to \mathbb{P}^1 - \{0,1,\infty\}; \tau \mapsto \mathbb{C}/ (\mathbb{Z} + 2\mathbb{Z}) \mapsto y^2 = x(x-1)(x-\lambda)$


> [!Definition]
> $k \in \mathbb{Z}$, $\Gamma = \Gamma(N), \Gamma_0(N), \Gamma_1(N)$
> $f: \mathbb{H} \to \mathbb{C}$ is a modular form of weight $kk$ and level $\Gamma$ if $f|_k \gamma(\tau) = g(\tau)$ for any $\gamma \in \Gamma$; here, $f|_k \gamma (\tau) = f(\gamma \tau) \cdot j(\gamma \tau)^{-k}$ where $j(\gamma \tau) = \det \gamma^{-\frac{1}{2}} (c\tau + d)$

There is also a notion of $f$ being holomorphic at a cusp; 

Say that $\begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \in \Gamma$. We have $f|_{k} \gamma(\tau) = f(\tau+1)$, so we have a Fourier series $f(\tau) = \sum_{n=-\infty}^\infty a(n) q^n$ where $q = e^{2 \pi i \tau}$.  


$f$ is holomorphic at a cusp if $a(n) = 0$ for $n < 0$ and it is cuspidal it is $a(0) = 0$.


Examples 

1. Eisenstein series $\Gamma_\infty = \begin{pmatrix} 1 & * \\ 0 & 1 \end{pmatrix}$
$$G_k(\tau) = \frac{1}{2} \sum_{\Gamma_\infty \backslash \operatorname{SL}_2(\mathbb{Z})} 1|_k \gamma = \frac{1}{2} \sum_{\substack{c,d \in \mathbb{Z} \\ (c,d) = 1} } \frac{1}{(cz+d)^k} \in M_k(\Gamma(1))$$


$$E_k(\tau) = \zeta(k) G_k(\tau) = \frac{1}{2} \sum \frac{1}{(c\tau+d)^k}$$


2. $\Delta(\tau) = \frac{1}{1728} (G_4^3 - G_6^2) \in S_{12}(\Gamma(1))$

3. Jacobi theta function $\theta(q) = \sum_{n \in \mathbb{Z}} q^{n^2}$

$\theta(\tau+1) = \theta(\tau)$

$$\theta \left(-\frac{1}{4\tau} \right) = (-2 \pi i \tau)^{\frac{1}{2}} \theta(\tau)$$

$$\theta(\tau) \in M_{\frac{1}{2}} (\Gamma_1(4))$$



# Why do we care about modular forms?

Say that $f$ is a Hecke eigenform, normalized, cuspidal, newform of weight $2$. We can then construct the $L$-function


$$L(f,s) = \sum_{n \geq 1} a(n) n^{-s} = \prod_{p \mid N} L_p(f,s) \cdot \prod_{p \nmid N} (1-a(p) p^s + p^{1-2s})^{-1}$$

Such a modular form corresponds to an elliptic curve $E/\mathbb{Q}$; also, $a(p) = p+1 - \# E(\mathbb{F}_p)$


> [!Comment]
> $M(\Gamma_0(N), \chi)$ where $\chi: (\mathbb{Z}/N)^ \times \to \mathbb{C}$, consists of the holomorphic functions such that 
>
> $$f\left( \begin{pmatrix} a & b \\ c & d \end{pmatrix} \tau \right) = \chi(d) (c\tau+d)^k f(\tau)$$
>
> Note that $M(\Gamma_0(N), \chi) \subset M(\Gamma_1(N))$ and that $\Gamma_0(N)/  \Gamma_1(N) \cong (\mathbb{Z}/N\mathbb{Z})$.

We have the decomposition

$$M(\Gamma_1(N)) = \bigoplus_\chi M(\Gamma_0(N), \chi)$$

For any congruence subgroup $\Gamma$, there is some $\alpha \in \operatorname{GL}_2(\mathbb{Q})$ such that $\alpha \Gamma \alpha^{-1} \subset \Gamma_1(N)$.


# 2. Automorphic forms


Let $G = \operatorname{GL}_2$, let $F = \mathbb{Q}$, and let $\mathbb{A} = \mathbb{A}_F$. Let $p$ be a place of $F$. Let $\mathbb{R} = F_\infty$

In general, we can replace $G$ with a nice reductive group, and $F$ with a general number field.

$G(\mathbb{A}) = G(\mathbb{R}) \cdot G(\mathbb{A}_f) = G(\mathbb{R}) \cdot \prod' G(\mathbb{Q}_p)$

Say that $K_f \subset G(\mathbb{A}_f)$ is an open compact subgroup. Equivalently, we can write $K_f = \prod K_p$ where $K_p = G(\mathcal{O}_p)$ for all but finitely many $p$.


> [!Theorem]
> (Strong approximation) Say that $\det (K_f) = \hat{\mathbb{Z}}^\times$. In this case, $G(\mathbb{A}) = G(\mathbb{Q}) G(\mathbb{R})^\oplus K_f$. 

Another way to say this is that $G(\mathbb{Q})$ is dense $G(\mathbb{A})$

Let $K_0(N) = \left\{ \begin{pmatrix} a & b \\ c & d \end{pmatrix}: c \equiv 0\pmod{N} \right\}$; $K_0(N)$ has matrices with entries over $\mathbb{A}_f$.

By strong approximation, we then have

$$G(\mathbb{Q}) \backslash G(\mathbb{A}) / K_0(N) \simeq \Gamma_0(N) \backslash G(\mathbb{R})^+$$.

Also, note that $G(\mathbb{R})^+ = Z(\mathbb{R}) \cdot \operatorname{SL}_2(\mathbb{R})$, and there is an isomorphism $\operatorname{SL}_2(\mathbb{R}) / \operatorname{SO}_2(\mathbb{R}) \xrightarrow{\sim} \mathbb{H}$. Here, $Z$ is the center of $G$. In this case, $Z$ consists of the scalar matrices. Therefore, this tells us that $f: \mathbb{H} \to \mathbb{C}$ should come from $\phi_f: \operatorname{GL}_2(\mathbb{Q}) \backslash \operatorname{GL}_2(\mathbb{A}) \to \mathbb{C}$.

First let's define $\phi_f: G(\mathbb{R})^+ \to \mathbb{C}$, and then the isomorphism given by strong approximation will give us the map $\operatorname{GL}_2(\mathbb{Q}) \backslash \operatorname{GL}_2(\mathbb{A}) \to \mathbb{C}$.

Define $\phi_f(g_\infty) = f(g_\infty i) j(g_\infty , i)^{-k}$


> [!Proposition]
> Say that $f \in M_k(\Gamma_0(N))$ Then 
> 1. $j(g_1g_2, \tau) = j(g_1 g_2(\tau)) j(g_2 \tau)$, 
> 
> $j(zk\theta, i) = \operatorname{sgn}(z) e^{-i \theta}$ where $z \in Z(\mathbb{R})$, $k_\theta = \begin{pmatrix} \cos \theta & \sin \theta \\ -\sin \theta  &\cos \theta \end{pmatrix}$ 
> 
> $j(z,i) = \operatorname{sgn}(z) j(k_\theta, i) = e^{-i\theta}$
>
> 2. For $\gamma \in \Gamma_0(N)$, $\phi(\gamma g_\infty) = \phi(g_\infty)$
> 3. $\phi_f(g_\infty, zk_\theta) = \phi(g_\infty) \operatorname{sgn}(z)^k (e^{i\theta})^k$

Let $\mathfrak{g}$ be the Lie algebra of $\operatorname{GL}_2(\mathbb{R})^+$. Write $\hat{L} = \begin{bmatrix} & 0 \\ 1 & \end{bmatrix}$, $\hat{R} = \begin{bmatrix} & 1 \\ 0 & \end{bmatrix}$, $\hat{H} = \begin{bmatrix} 1 &  \\  & -1 \end{bmatrix}$, $\begin{bmatrix} 1 &  \\  & 1 \end{bmatrix}$. Construct the universal enveloping algebra $U(\mathfrak{g})$. The center $Z(U(\mathfrak{g}))$ is an algebra generated by two elements; $Z(U(\mathfrak{g})) \cong \mathbb{C}[Z, \Delta]$, where $\Delta$ is the Casimir operator defined by $-\frac{1}{4}(\hat{H}^2 + 2\hat{R}\hat{L} + 2\hat{L}\hat{R})$.

We have a Lie algebra action of $\mathfrak{g}$ on automorphic forms: for $x \in \mathfrak{g}$, 

$$x \phi_f(g_\infty) = \frac{d}{dt} \phi_f(g_\infty(I+Xt)) |_{t=0}$$

We then have

$$Z \phi_f = 0$$
$$\Delta \phi_f = -\frac{1}{4} k(k-2) \phi_f$$

these two equations correspond to/explain the central character and holomorphicity

# 3. Automorphic representation

Let $\omega: \mathbb{Q}^\times \backslash \mathbb{A}^\times \to \mathbb{C}$ be a character of the ideles.

> [!Definition]
> The space $\mathcal{A}(G, \omega)$ of automorphic forms is the space "smooth" functions $f:G(\mathbb{Q}) \to \mathbb{C}$ (in the archimedean places, smoothness is the usual notion; in the nonarchimedean places, smoothness means locally constant) such that
> 1. for $z \in Z(\mathbb{A})$, $f(zg) = \omega(z) f(g)$[^1] and for $\gamma \in G(\mathbb{Q})$, we have $f(\gamma g) = f(g)$
> 2. Let $K_\infty = \operatorname{SO}_2(\mathbb{R})$; the action of $K_\infty$ on the right of $f$ is finite, i.e. $\dim_\mathbb{C} K_\infty f < \infty$.
> 3. There exists an open compact subgroup $K_f \subset \operatorname{GL}(\mathbb{A}_f)$ such that $K_f f = f$.
> 4. The action of $Z(U(g))$ is also finite.
> 5. Analytic growth condition

[^1]: This is analogous to $f(\gamma \tau) = \chi(d) f(\tau)$













# See Also

# Meta
## References

## Citations and Footnotes