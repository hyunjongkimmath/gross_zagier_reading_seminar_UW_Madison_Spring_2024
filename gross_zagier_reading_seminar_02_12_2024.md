---
cssclass: clean-embeds
aliases: []
tags: [_meta/self_written, _meta/notes]
---
# Weil represntations and $\Theta$ functions

Speaker: Ryan Tamura


(i) Weil representations provide a generalization of $\Theta$-functions whichcan be viewed as automorphic of $MP(w)$ and dual pairs of $Sp(w)$.

(ii) $\Theta$-correspondence: correspondence between smooth irreducible rperesnetations of $G$ and "" of $\Theta$, where $(\Theta, \Theta')$

# 1. Heisenberg Groups and Representations

Setup: Local field $F$ and a symplectic vector space $W/F$ with a pairing: $(W, ()_W)$

> [!Definition]
> (Heisenberg group):
> $H(W) = W \times F$, twisted product $(w,f) \cdot (w',f') = (w+w', f+f'+\frac{1}{2}(w,w')_W)$

Example: take $F = \mathbb{R}$ with dimension 2 symplectic space over $\mathbb{R}$, and then

$$H(W) = \{ \begin{pmatrix} 1 & a & c \\ 0 & 1 & b \\ 0 & 0& 1 \end{pmatrix} : a,b,c \in \mathbb{R} \}$$

> [!Remark]
> $H(W)$ can be viewed as a central extension
> $$1 \to F \to H(W) \to W \to 1$$
> and $Z(H(W)) = ((0,f): f \in F) \cong \mathcal{F}$


Philosophy: irreducible representations of $H(W)$ are given by Schwartz functions.



> [!Theorem]
> (Stone-Von Neumann):
> Start with a nontrivial additive character $\psi: (F, +) \to \mathbb{C}^*$
> 
> Then there is a unique (up to isomorphism) irreducible, smooth, admissible representation $(p_\psi, S_\psi)$ where $Z(H(W))$ central character $\psi$, i.e. $(0, f) \circ V = \rho(f)_V$


## Idea of the proof of existence

> [!Remark]
> $S_\psi$ concrete model of $S_\psi$ Schrodinger model

Since $W$ is a symplectic space, we can take a decomposition $W = X \oplus Y$ where $X,Y$ are maximal isotropic subspaces

Define 
$$\operatorname{Ind}^{H(W)}_{Y \times F} \psi =  \{\varphi: H(W) \to \mathbb{C} \text{ satisfying the below listed conditions }\}$$

(i) $\varphi((y,f) \cdot h) = \psi(f) \circ \varphi(h)$

(ii) there exists an open compact neighborhood $v \subseteq H(W)$ such that for $(v,0) \in V$, for any $h \in H(W)$, we have $\varphi((v,0) h) = \varphi(h)$ 

There is an action: for $h \in H(W)$, let

$$(h \circ \varphi)(h') = \varphi(h' \circ h).$$

We also have a map 

$$i: X \to H(W), \quad X \mapsto (x,0)$$

and a map

$$S_Y \to S(X) = \{f: X \to \mathbb{C}, \text{ compactly supported and locally constant } \}, \quad f \mapsto f \circ i$$


Let $(h,f) \in H(W)$. We want to define $(h,f) \circ \varphi(X)$

Decompose $W = X \oplus Y$, set $h = x+y$. So we are defining $(x+y, f) \circ \varphi(x)$:

$$(x+y, f) \circ \varphi(x_0) = \psi(f + (x_0, y)_W + \frac{1}{2}(x,y)_W) \circ \psi(x+x_0))$$

And then $Z(H(w)) = \{(0,f)\}$ acts by $\psi$. 

The irreducible smooth representation of the Heisenberg group is in disguise the space of Schwarz functions (is what I think Ryan said).


> [!Comment]
> Simon Marshall comments that Heisenberg is involved because this relates position and momentum; there is a quantum mechanical thing going on here.

# Local Weil representation

Define a right action of $\operatorname{Sp}(W)$ on $H(W)$: for $\sigma \in \operatorname{Sp}(W)$, 

$$(h,f) \sigma = (h\sigma, f)$$


Now define the twist of $p_\psi$ by $\sigma$:

$(p^\sigma \psi, S_\psi), p^\sigma \psi((h,f)) = p_\psi((h,f) \circ \sigma)$

> [!Proposition]
> The central characters of $p_\psi$ and $p_\psi^\sigma$ are the same

> [!Theorem]
> $(p_\psi, S_\psi) \simeq (p_\psi^g, S_\psi)$, but this isomorphism is not canonical. 

We have the Projective Weil representation

$$w: \operatorname{Sp}(W) \to \operatorname{PGL}(S_\psi) = \operatorname{GL}(S_\psi) / \mathbb{C}^*$$

where $w(\sigma) = [A(g)]$ such that 

$$A(\sigma) p_\psi A(\sigma)^{-1} = p_\psi^\sigma$$

> [!Remark]
> $H^2(\operatorname{Sp}(W), \mathbb{C}^*) \neq 0$


> [!Definition]
> (Metaplectic group)
> The Metaplectic group $\operatorname{Mp}(W)_\psi$ is the fiber product of $\operatorname{Sp}(w) \xrightarrow{w} \operatorname{PGL}(S_\psi)$ and $\pi: \operatorname{GL}(S) \to \operatorname{PGL}(S_\psi)$. 
>
> The induced map $\tilde{\omega}: \operatorname{Mp}(w)_\psi) \to \operatorname{GL}(S_\psi)$ is the Local Weil representation of $\psi$

We also have

$$\operatorname{Mp}_\psi(W) =  \{(\sigma, \Phi) , \Phi _\psi \Phi^{-1} = p_\psi^\omega \}$$


> [!Theorem]
> (The metaplectic group doesn't depend on the non-trivial character $\psi$)
> 
> from $r: \operatorname{Sp}(W) \to \operatorname{Mp}(W)$, get an explicit $2$ cocycle 
> $$(\sigma, r(\sigma)) \circ (\sigma_1', r(\sigma')) = (\sigma\sigma', c_2(\sigma \rho') r(\sigma\sigma'))$$

$$1 \to \mathbb{C}^* \to \operatorname{Mp}(W) \to \operatorname{Sp}(W) \to 1$$

$$\operatorname{Mp}_{\text{rao}}(w) = \operatorname{Sp}(W) \times \mathbb{C}^* = \{(\sigma, z ) \} \text{ product } (\sigma,z)(\sigma',z') = (\sigma\sigma', c_{\text{rao}}(\sigma, \sigma') zz')$$


## Examples
Take $\operatorname{Sp}_2(F) = \operatorname{SL}_2(F)$, we can take $P$ to be the maximal parabolic subgroup, where $P = MN$ where 
$$M = \left\{\begin{pmatrix} a & 0 \\ 0 & a^{-1} \end{pmatrix} \right\}, N = \left\{ \begin{pmatrix} 1 & b \\ 0 & 1 \end{pmatrix} \right\}, a,b, \in F$$


there are then formulae

- (i) $$\omega \left( \begin{pmatrix} a & 0 \\ 0 & a^{-1} \end{pmatrix}, z \right) \varphi(x) = z|a|^{1/2} \varphi(ax)$$
- (ii) $$\omega\left( \begin{pmatrix} 1 & b \\ 0 & 1 \end{pmatrix}, z \right) \varphi(x) = \psi\left( \frac{b}{2} x^2 \right) \varphi(x)$$
- (iii) $\omega\left( \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}, z \right) \varphi(x) = z S_V \circ \varphi(x)$

...

# 

Take $K$ to be a number field, $\psi: \mathbb{A}_K \to \mathbb{C}^*$. Take $W/F$ to be a symplectic space

$$1 \to \mathbb{C}^* \to \operatorname{Mp}(W) \to \operatorname{Sp}(W) \to 1$$

(i) Take the restricted product

$$\tilde{\operatorname{Mp}}(W) = \prod_v' \operatorname{Mp}(W_V) = \{(g_v) : g_v \in \mathcal{O}_{K,v} \text{ for all but finitely many } v \}$$

> [!Definition]
> (Adelic metaplectic group)
> $\operatorname{Mp}(W) = \widetilde{\operatorname{Mp}(W)} / H$ where $H \leq \bigoplus \mathbb{C}$

> [!Definition]
> (Weil representation)
> This is the representation
> $$\bigoplus_v' S_{\psi, v} = \varinjlim_{S \text{ finite set of places}} \otimes_{v \in S} S_{\psi, V} = S \otimes (\mathbb{A})$$



# See Also

# Meta
## References

## Citations and Footnotes