---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# Shimura varieties and their special cycles - in the case of O(0,2), O(1,2), and O(2,2) 



Speaker: [[dao_kevin]]

Outline:
1. Generalities on Shimura v arieties
2. Orthogonal Shimura varieties
3. Special cycles
4. More examples

# 1 Shimura varieties

> [!Definition (vague)]
> Let $(G, \mathbb{D})$ be a reductive algebraic group and a complx symmetric space. If this pair satisfies some conditions and $G$ acts on $\mathbb{D}$ in some way, then this is a Shimura datum.
> From a Shimura datum and given an open compact $K \subseteq G(\mathbb{A}_f)$, one can construct a double coset
> $$X_K = G(\mathbb{Q}) \backslash \mathbb{D} \times G(\mathbb{A}_f) / K$$

The $X_K$'s are very nice to study. Also the action is as follows:

$$\begin{align*}
g[x,h] &= [gx,gh] \\
[x,h]k &= [x,hk]
\end{align*}$$

> [!Properties]
> (Important) 
> $X_K$ decomposes as a disjoint union 
> $$\coprod_{j} \Gamma_j \backslash \mathbb{D}^+$$
> of connected; here, $\Gamma_j = G(\mathbb{Q})_+ \cap g_j K g_j^{-1}$ and the $g_j$'s are double coset representatives of $G(\mathbb{Q})_+ \backslash G(\mathbb{A}_f) / K$

> [!Theorem]
> (Reflex)
> the $X_K$'s are defined over a number field called the <b style="border-width:1px;border-style:solid;padding:3px" definition="">reflex field</b>. Moreover, the reflex field does not depend on $K$.


> [!Example]
> Let $G = \operatorname{GL}_2$, $K  = \ker(\operatorname{GL}_2(\hat{\mathbb{Z}}) \to \operatorname{GL}_2(\mathbb{Z}/N\mathbb{Z}))$. Let $\mathbb{D} = \{G(\mathbb{R})\text{-conjugacy classes of a map } h_0 : \mathbb{S} \to \operatorname{GL}_{2,\mathbb{R}}, \quad a+bi \mapsto \begin{pmatrix} a & b \\ -b & a \end{pmatrix} \}$ 
> We get a decomposition
> $$X_K = \coprod_{\mathbb{Z}/N\mathbb{Z}^\times} Y(\Gamma(N))$$ where $Y(\Gamma(N))$ is constructed as $\mathbb{H} / \Gamma(N)$


> [!Computation]
> How do we know that the components correspond to elements of $\mathbb{Z}/N\mathbb{Z}^\times$? We need to see what the double coset representatives of $\operatorname{GL}_2(\mathbb{Q})_+ \backslash \operatorname{GL}_2(\mathbb{A}_f) / K$ are:
> $$\begin{align*}
> \operatorname{GL}_2(\mathbb{Q})_+ \backslash \operatorname{GL}_2(\mathbb{A}_f) / K &= \operatorname{GL}_2(\mathbb{Q})_+ \backslash \operatorname{GL}_2(\mathbb{Q}) \operatorname{GL}_2(\hat{\mathbb{Z}}) / K \\
> &= (\mathbb{Z}/N\mathbb{Z})^\times
> \end{align*}$$

# 2. Orthogonal Shimura varieties


Here is the setup:
1. Let $(V, Q)$ be an quadratic space of signature $(n,2)$[^1].
2. $C(V) = T(V) / (V^2 - Q(v))$ is the Clifford algebra. It decomposes as $C(V) = C^{\text{even}} \oplus C^{\text{odd}}(V)$, and we have an embedding $V \hookrightarrow C^{\text{odd}}(V)$.

[^1]: It turns out that only signature $(n,2)$ quadratic spaces give Shimura varieties

Write $G = \operatorname{GSpin}(V) = \{g \in C^{\text{even}}(V)^\times : gVg^{-1} = V\}$



## Table of accidental isomorphisms

| $\dim V = n+2$ | $C^{\text{even}}(V)$                                          | $\operatorname{GSpin}(V)$                                                                                                                                            |
| -------------- | ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| $\dim V = 2$   | Imaginary quadratic field $K$                                 | $\operatorname{Res}_{K/\mathbb{Q}} \mathbb{G}_{K,m} \simeq K^\times$                                                                                                 |
| $\dim V = 3$   | Quaternion algebras over $\mathbb{Q}$                         | $\operatorname{GL}_2$ or $B^\times$ (indeterminate quaternion algebra $B$)                                                                                           |
| $\dim V = 4$   | Quaternion algebras over the center $Z((C^{\text{even}}(V)))$ | $\operatorname{GL}_2 \times_{\mathbb{G}_m} \operatorname{GL}_2$ or $\operatorname{GL}_{2,F}^{\det \in \mathbb{Q}^\times}$, $B^\times \times_{\mathbb{G}_m} B^\times$ |

## An example of why these happen for $n = 0$


Let $(V,Q)$ is a quadratic space and say that $V$ has an orthogonal basis $\{e_1,e_2\}$: $V = \mathbb{Q} e_1 \oplus \mathbb{Q} e_2$. The Clifford algebra decomposes as

$$C(V) \cong \mathbb{Q} \oplus \mathbb{Q} e_1 \oplus \mathbb{Q} e_2 \oplus \mathbb{Q}(e_1 \otimes e_2)$$

and 

$$C^{\text{even}}(V) \cong \mathbb{Q}[X] / (X^2+q_1q_2)$$

where $q_i = Q(e_i)$. This isomorphism then tells you that


$$C^{\text{even}}(V)^\times \cong \mathbb{Q}(\sqrt{-q_1q_2})^\times$$


> [!Remark]
> Relationship between $\operatorname{SO}$ and $\operatorname{GSpin}$: there is a short exact sequence
> $$1 \to \mathbb{G}_m \to \operatorname{GSpin}(V) \to \operatorname{SO}(V) \to 1;$$
> Here, $g \in \operatorname{GSpin}(V)$ is sent to the element of $\operatorname{SO}(V)$ which acts on $V$ via $gVg^{-1}$.
> Moreover, in this case, $\operatorname{SO}(V)$ is the group of norm $1$ elements of $K^\times$.

Example Orthogonal $\operatorname{Sr}$ associated to $O(0,2)$

Let $k = \mathbb{Q}(\sqrt{d})$ with $d < 0$. Let $G = k^\times$. Let $\mathbb{D}$ be the Grassmannian of regular definite oriented $2$  planes in $V(\mathbb{R})$. There are $2$ orientations of $V_\mathbb{R}$, denoted by $z_0^{\pm}$. Let $K = \hat{\mathcal{O}_k}^\times \subseteq \mathbb{A}_{f,k}^\times$. Let We have $X_K = k^\times \backslash \{z_0^\pm\} \times \mathbb{A}_{f,k}^\times / \hat{\mathcal{O}}_k^\times = \{z_0^+ \} \times \operatorname{Cl}(k)$. 

Why is this?

We need to count the number of connected components.

We have $k^\times \backslash \mathbb{A}_{f,k}^\times / \hat{\mathcal{O}}_k^\times = \operatorname{Cl}(k)$, and then we can decompose $X_K$ as

$$X_K  = \coprod_{\operatorname{Cl}(k)} \Gamma_{y_j} \backslash \mathbb{D}^+ = \coprod_{\operatorname{Cl}(K)} \{z_0^+\}.$$



# 3. Special Cycles (Kudla 1997)

How do we construct special cycles?

> [!Definition]
> Let $(V,Q)$ be a quadratic space with signature $(n,2)$. Pick $x \in V(\mathbb{Q})$ such that $Q(x) > 0$. Write $V_x = x^\perp$. It is a quadratic space of signature $(n-1,2)$. Then $\mathbb{D}_x \subseteq \mathbb{D}$ is the corresponding negative definite plane; it has a point $z$ with $z \perp x$.

We have a map, where $G_j$ is the subset of $G$ of stabilizers of $x$.

$$G_x(\mathbb{Q}) \backslash \mathbb{D}_x \times G_x(\mathbb{A}_f)/ G(\mathbb{A}_f) \cap K \to X_K = G(\mathbb{Q}) \backslash \mathbb{D} \times G(\mathbb{A}_f) / K$$

The image of this map is $Z(x;K)$


## Shifted cycles

$Z(x,g,K)$ is defined as the image of the map

$$G_x(\mathbb{Q}) \backslash \mathbb{D}_x \times G_x(\mathbb{A}_f) / K \cap G_x(\mathbb{A}_f) \to X_K$$

sending $[x,h] \mapsto [x,hg]$ where $g \in G(\mathbb{A}_f)$; this is the same kind of map as before, except you shift the connected component that you land one.

## Special cycles

What are special cycles? 

> [!Definition]
> Let $\varphi \in \mathcal{S}(V(\mathbb{A}_f))^K$ be a $K$-invariant Schwarz function, let $m \in \mathbb{Q}$, and let $x \in V(\mathbb{Q})$. Then
> $$Z(m,\varphi,K) = \sum_j \varphi(g_j^{-1} x) \cdot Z(x,g_j; K);$$
> this is a finite sum over the representatives $g_1,\ldots,g_r$ of  $K \backslash \operatorname{Supp} \varphi \cap \Omega_m(\mathbb{A}_f)$. Here, $\Omega_m(\mathbb{A}_f) = \{x \in V(\mathbb{A}_f) : Q(x) = m \}$.

> [!Lemma 4.1 / Kudla Proposition 5.4]
> If $G(\mathbb{A}_f) = G(\mathbb{Q})_+ K$, then $Z(m,\varphi;K) = \sum_{x \in \Gamma_K \backslash \Omega_m(\mathbb{Q})} \varphi(X) \operatorname{pr}(\mathbb{D}_x, 1)$ where $\Gamma_K = G(\mathbb{Q})_+ \cap K$ and $\operatorname{pr}: \mathbb{D}_x \times G(\mathbb{A}_f) \to X_K$

This is useful for computations.


### Examples

There is a general procedure by which you can construct special cycles.

> [!General procedure]
> Typically, you are going to take
> 1. A (even integral) lattice $L \subseteq V(\mathbb{Q})$ 
> 2. $\varphi = \sum_{\mu \in \text{Orbits in } L^\vee / L} \operatorname{char}(\mu + \hat{L}) \in \mathcal{S}(V(\mathbb{A}_f))^K$
> 3. Get "nice" special cycles $Z(m,\varphi; K)$


### Examples

Heegner points on $X_0(N)$

Let $V = M_2(\mathbb{Q})^{\text{Tr} = 0}$, let $Q(x) = N \cdot \det(x)$. Then $\operatorname{GSpin}(V) \cong \operatorname{GL}_2$, and $\operatorname{GL}_2(\mathbb{Q})$ acts on $V$ via $g \cdot x = gxg^{-1}$. Moreover, $\operatorname{SO}(V) = \operatorname{PGL}_2$.

Now consider the biholomorphic map 

$$\mathbb{H}^{\pm } \to \mathbb{D}, \quad x+iy = z \mapsto \begin{pmatrix} z & z^2 \\  1 & -z \end{pmatrix}$$

We have

$$K = \prod K_p \subseteq G(\mathbb{A}_f)$$

where $K_p = \{ \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in \operatorname{GL}_2(\mathbb{Z}_p) : c \in N \cdot \mathbb{Z}_p \}$.

> [!Fact]
> $G(\mathbb{A}_f) = G(\mathbb{Q}) K$

We also have

$$X_K = K \cap G(\mathbb{Q})_+ \backslash \mathbb{D}^+ = \Gamma_0(N) \backslash \mathbb{H} = Y_0(N)$$



# Classical Heegner divisors

Take $P_{D,r} + P_{D,-r}$ on $X_0(N)$; here,

$$P_{D,r} = \{ z \in X_0(N) : az^2 + bz + c = 0, a > 0 , a \equiv 0 \pmod{N}, b \equiv 0 \pmod{-r} \pmod{2N}, b^2 - 4ac = D \}$$

[^2]

[^2]: Here, we are regarding $z$ as representing a point in $\mathbb{H} \subseteq \mathbb{C}$.

(This is Gross-Kohren-Zagier)


> [!Claim]
> $Z(\cdot, \varphi; K) = P_{D,r} + P_{D,-r}$

## Step 1: Make a Schwarz function

Let $L = \{ \begin{pmatrix} b & -q/N \\ c & -b \end{pmatrix} : a,b,c \in \mathbb{Z} \}$. It turns out that $L^\vee / L \cong \mathbb{Z} / 2N\mathbb{Z}$ where $r \in \mathbb{Z}/2N\mathbb{Z}$ correspnods to $\begin{pmatrix} \frac{r}{2N} & 0 \\ 0 & -\frac{r}{2N} \end{pmatrix}  r$.


## Step 2:

Claim: $K$ acts on $L^\vee / L$ trivially.

## Step 3:

So $\varphi = \operatorname{char}( \begin{pmatrix} \frac{r}{2N} & 0 \\ 0 & -\frac{r}{2N} \end{pmatrix} + \hat{L} )$

There is a lemma from Bruinier-Yang that says that 

$$Z(m,\varphi,K) = \sum_{x \in \Gamma_K \backslash \Omega_m(\mathbb{Q})} \varphi(x) \operatorname{pr}(\mathbb{D}_x, 1)$$


$\mathbb{D}_x$ consists of 

$$0 = (x, \omega(z)) = -N \operatorname{Tr} \begin{pmatrix} \frac{r}{2N} & \frac{1}{N} \\ \frac{D-r^2}{4N} & - \frac{r}{2N} \end{pmatrix} \begin{pmatrix} z & -z^2 \\ 1 & -z \end{pmatrix} = \cdots = \frac{D-r^2}{4} z^2 - rz - 1$$

Here, $D= -4Nm \in \mathbb{Z}$

### Last thing to check/compute

$$\Gamma_K \backslash \Omega_m (\mathbb{Q}) \cap \operatorname{Supp}(\varphi) \ni x$$









# See Also

# Meta
## References

## Citations and Footnotes