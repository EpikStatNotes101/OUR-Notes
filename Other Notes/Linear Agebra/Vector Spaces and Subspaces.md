# Vector Space
A nonempty set of vectors $V$ is a subspace if it satisfies the following for all $\bf{u, v, w} \in V$ and $c, d \in \mathbb{R}$ :

| name           | vector addition                                            | scalar multiplication                        |
| -------------- | ---------------------------------------------------------- | -------------------------------------------- |
| commutativity  | $\mathbf{u+v = v+u}$                                       | -                                            |
| associativity  | $(\mathbf{u+v}) + \mathbf{w}= \mathbf{u} + (\mathbf{v+w})$ | $c(d\mathbf{u}) = (cd)\mathbf{u}$            |
| distributivity | $c(\mathbf{u+v})= c\mathbf{u} + c\mathbf{v}$               | $(c+d)\mathbf{u}= c\mathbf{u} + d\mathbf{u}$ |
| identity       | $\mathbf{u+0}= \mathbf{u}$                                 | $1\mathbf{u}= \mathbf{u}$                    |
| inverse        | $\mathbf{u+(-u)}= \mathbf{0}$                              | -                                            |
| closure        | $\mathbf{u+v}\in V$                                        | $c\mathbf{u}\in V$                           |

# Subspace
A set $H \subset V$ is a subspace if :

- the $\mathbf{0}$ vector is in $V$
- $H$ is closed under vector addition. That is for any $\mathbf{u,v} \in H$, $\mathbf{u+v}\in H$
- $H$ is closed under scalar multiplication. That is for any $\mathbf{v} \in H$ and $c \in \mathbb{R}$, $c\mathbf{v}\in H$ 

# Null Space
For a $m\times n$ matrix $A$, the null space is the set of vectors which satisfies the equation $A\mathbf{x=0}$. 

$\text{Nul }A=\{\mathbf{x:x} \in \mathbb{R}^n \text{ and } A\mathbf{x=0}\}$ 

# Column Space
For a $m\times n$ matrix $A$, the null space is the set of all possible linear combinations of the columns of $A$. That is if $A = \left[\mathbf{a_1 \text{ ... } a_n}\right]$ 






