
# Stochastic Processes 
#### Safalya Pal - A90555919003

### Q1. 
Consider the experiment in which we record $M(t)$, the number of active calls at a telephone switch at time $t$, for each second over an interval of 15 minutes. Determine the state space and the index set of the stochastic process $\left\{M(t):t\geq 0\right\}$.

#### Answer
State space $S_X  =\left\{0, 1, 2, ...\right\}$
Index set $T_X = \left\{0, 1, 2, ...\right\}$

### Q2. 
6 green balls and 4 white balls are placed in two boxes $A$ and $B$ such that each box has 5 balls. At each stage, a ball is drawn at random from each box and two balls are interchanged.

a) Let $X_n$ denote the number of white balls in box $A$ after the $n^{\text{th}}$ draw. Find the state space and the index set of the stochastic process $\left\{X_n\right\}$.

b) Let $Y_n$ denote the number of green balls in box $A$ after the $n^{\text{th}}$ draw. Find the state space and the index set of the stochastic process $\left\{Y_n\right\}$.

#### Answer 
##### part (a)
State space $S_X = \left\{0, 1, 2, 3, 4\right\}$
Index set $T_X = \left\{0, 1, 2, ...\right\}$
##### part (b)
State space $S_Y = \left\{0, 1, 2, 3, 4, 5\right\}$
Index set $T_Y = \left\{0, 1, 2, ...\right\}$

### Q3. 
A box contains 3 black and 7 white balls. At each trial, a ball is drawn randomly from the box. If it is white, it is put back into the box and if it is black, it is kept outside the box. Let $X_n$ denote the number of black balls taken out of the box after the $n^{\text{th}}$ trial. Find the state space and the index of the stochastic process $\left\{X_n\right\}$.

#### Answer 
State space $S_X = \left\{0, 1, 2, 3\right\}$
Index set $T_X = \left\{0, 1, 2, ...\right\}$

### Q4.
Suppose a coin is tossed 15 times. Let $X_n$ denote the total number of "heads" which appear up to the $n^{\text{th}}$ toss. Find the state space and the index set of the stochastic process $\left\{X_n\right\}$.

#### Answer 
State space $S_X = \left\{0, 1, 2, ..., 15\right\}$
Index set $T_X = \left\{0, 1, 2, ..., 15\right\}$

### Q5. 
Consider an acceptance sampling plan. Let $D_n$ denote the number of defective items after inspecting $n$ items. Find the state space and the index set of the stochastic process $\left\{D_n\right\}$.

#### Answer 
State space $S_D = \left\{0, 1, 2, ...\right\}$
Index set $T_D = \left\{0, 1, 2, ...\right\}$

### Q6. 
$M$ coins are placed in a row on a table. At each stage, a coin is selected at random and turned over. Let $X_n$ denote the total number of "heads" out of the $M$ coins after the $n^{\text{th}}$ trial. Find the state space and the index set of the stochastic process $\left\{X_n\right\}$.

#### Answer 
State space $S_X = \left\{0, 1, 2, ..., M\right\}$
Index set $T_X = \left\{0, 1, 2, ...\right\}$

### Q7. 
2 white balls and 5 green balls are placed in two boxes $A$ and $B$ so that box $A$ contains 4 balls and box $B$ contains 3 balls. At each stage, one ball is selected at random from each box and the two balls are interchanged. Let $Y_n$ denote the number of white balls in box $A$ at the $n^{\text{th}}$ trial. Find the state space and the index set of the stochastic process $\left\{Y_n\right\}$.

#### Answer 
State space $S_Y = \left\{0, 1, 2\right\}$
Index set $T_Y = \left\{0, 1, 2, ...\right\}$

### Q8. 
John and Alice start a game with \$3 each as their capital. At the end of every game, the loser pays \$1 to the winner. With every game played, the probability of John winning is 0.6 and the probability of Alice winning is 0.4. They quit playing when one of them loses all his/her capital. Let $C_n$ be the balance of John after $n$ games. Find the state space and the index set of the stochastic process $\left\{C_n\right\}$.

#### Answer 
State space $S_C = \left\{0, 1, 2, 3, 4, 5, 6\right\}$
Index set $T_C = \left\{0, 1, 2, ...\right\}$

### Q9. 
Let $Y_1, Y_2, ...Y_n$ be a sequence of iid random variables with mean $E(Y_i)=0$ and $V(Y_i)=4$ Define the discrete time random process $\left\{X_n, n \in N\right\}$ as

 $X_n= Y_1+Y_2+...+ Y_n$ for all $n\in N$

a) Find the mean function $X_n$
b) Find the autocorrelation function and covariance function for $X_n$

#### Answer
##### part (a)
Mean function,
$\mu_X(n)=E[X_n]=E[Y_1+Y_2+...+Y_n]=E[Y_1]+E[Y_2]+...+E[Y_n]=0$

##### part (b)
Autocorrelation function, 
$$\therefore R_X(m,n)=E[X_m \cdot X_n]$$
$$\begin{align}
&= &E[(Y_1+Y_2+...+Y_n)(Y_1+Y_2+...+Y_m)] \\
&= &E[Y_1^2]+E[Y_2^2]+...+E[Y_1Y_2]+E[Y_1Y_3]+...+E[Y_nY_m]\\
&= &4\cdot\min{(m,n)}\\
\end{align}$$

Covariance function:
$$\because E[X_n] = E[X_m] = 0,$$
$$ C_X(m, n) = \text{Cov}(X_m, X_n)=R_X(m,n)=4\cdot\min{(m,n)}$$

### Q10.
Consider the random process $X_n =1000(1+R)^n$ for $n=0,1,2,...$ where 
$$R\sim U(0.04,0.05)$$

a) Find the mean function of $X_n$
b) Find the autocorrelation function and covariance function for $X_n$

#### Answer
$$R\sim U(0.04,0.05)$$

$$X_n=1000(1+R)^n$$

Let $$Y=1+R$$

$$\therefore \; Y\sim U(1.04,1.05)$$

$$\therefore \; f_Y(y) = \left\{\begin{align}
&100,	&1.04 \leq y \leq 1.05 \\
&0,		&\text{o.w.}
\end{align}\right.$$
##### part (a)
Mean function, 
$$\therefore \; \mu_X(n) = 1000\cdot E[Y^n] = 1000\cdot\int_{1.04}^{1.05}100\cdot y^n\;dy$$
$$= \frac{100000}{n+1}\cdot \left[y^{n+1}\right]_{1.04}^{1.05}
=	\frac{100000}{n+1}\cdot \left(1.05^{n+1}-1.04^{n+1}\right)$$

##### part (b)
Autocorrelation function, 
$$R_X(m,n)=E[X_m \cdot X_n]$$
$$= E\left[1000\cdot Y^m \cdot 1000\cdot Y^n\right] = 10^6E\left[Y^{m+n}\right]=10^6\cdot\int_{1.04}^{1.05}100\cdot y^{m+n}\;dy$$
$$= \frac{10^8}{n+m+1}\cdot \left[y^{n+m+1}\right]_{1.04}^{1.05}
=\frac{10^8}{n+m+1}\cdot \left(1.05^{n+m+1}-1.04^{n+m+1}\right)$$

Covariance function, 
$$
\begin{split}

C_X(m,n)=\frac{10^8}{n+m+1}\cdot \left(1.05^{n+m+1}-1.04^{n+m+1}\right)   \\\\ -\frac{10^{10}}{(n+1)(m+1)}\cdot \left(1.05^{n+1}-1.04^{n+1}\right)\left(1.05^{m+1}-1.04^{m+1}\right)

\end{split}
$$
### Q11. 
A psychologist makes the following assumption concerning the behaviour of mice subjected to a particular feeding schedule. For any particular trial, $80\%$ of the mice that went right on the previous trial will go right on this trial, and $60\%$ of those mice that went left on the previous experiment will go right on this trial. If $50\%$ went right on the first trial, what would he predict for:

a) The second trial.
b) The third trial.
c) The thousandth trial.
	
#### Answer 
$$S=\left\{R, L\right\}$$
$$\therefore \;\; P=\left[\begin{matrix}
&0.8& 0.2& \\
&0.6& 0.4& \\
\end{matrix}\right]$$
$$\pi^{(0)} = \left[\begin{matrix} &0.5 &0.5 &\end{matrix}\right]$$

##### part (a)
$$\pi^{(1)} = \pi^{(0)} P$$
$$\Rightarrow \pi^{(1)} = \left[\begin{matrix} &0.7 &0.3 &\end{matrix}\right]$$
$\therefore\;$ for the second trial, there is $70\%$ chance that the mouse went right
##### part (b)
$$\pi^{(2)} = \pi^{(1)} P$$
$$\Rightarrow \pi^{(2)} = \left[\begin{matrix} &0.74 &0.26 &\end{matrix}\right]$$
$\therefore\;$ for the third trial, there is $74\%$ chance that the mouse went right
##### part (c)
Given $n$ is a number of trials, for $n=1000 \simeq \infty$, the distribution $\pi^{(\infty)}$ is given by the stationary distribution $\hat{p}$.

Let $\hat{p}=\left[\begin{matrix} &a &b &\end{matrix}\right]$
$$\therefore \; \hat{p} = \hat{p}P$$ 
$$\Rightarrow \; \left[\begin{matrix} &a &b &\end{matrix}\right] = \left[\begin{matrix} &a &b &\end{matrix}\right] 
\left[\begin{matrix}
&0.8& 0.2& \\
&0.6& 0.4& \\
\end{matrix}\right]$$

$$ \begin{align}
&\therefore &0.8a + 0.6b &= &a \\
&\Rightarrow &a &= &3b \\
\end{align}$$ 
..(1)

$$\because \;\; a + b = 1$$
..(2)

Substuting (1) to (2)

$$\begin{align}\\
&3b +b &= &1\\
&b &= &1/4\\
\end{align}$$

$$\therefore \;\; a = 3/4 = 0.75$$

$\therefore\;$ for the thousandth trial, there is $75\%$ chance that the mouse went right
### Q12.
Consider a markov chain which has the following transition matrix, 
$$P=
\left[\begin{matrix}
&0.7				&0.2			&0.1			& \\
&0					&0.6			&0.4			& \\
&0.5				&0				&0.5			& \\
\end{matrix}\right] $$
Determine, 

a)$P(X_1 = 1, X_2=1|X_0=0)$
b)$P(X_3=1|X_0=0)$
c)$P(X_2 = 1, X_3=1|X_0=0)$

#### Answer 
##### part(a)
$$P(X_1 = 1, X_2=1|X_0=0)$$
$$=P(X_2=1|X_1=1)\cdot P(X_1 = 1|X_0=0)$$
$$=p_{11}\cdot p_{01}$$
$$=0.6 \cdot 0.2=0.12$$

##### part(b)
$$P^{(3)}=PPP=
\left[\begin{matrix}
&0.478				&0.264			&0.258			& \\
&0.36				&0.256			&0.384			& \\
&0.57				&0.18			&0.25			& \\
\end{matrix}\right] $$

$$\therefore \; P(X_3=1|X_0=0)=p_{01}^{(3)}=0.264$$

##### part(c)
$$P^{(2)}=PP=
\left[\begin{matrix}
&0.54				&0.26			&0.2			& \\
&0.2				&0.36			&0.44			& \\
&0.6				&0.1			&0.3			& \\
\end{matrix}\right] $$

$$P(X_3 = 1, X_2=1|X_0=0)$$
$$=P(X_3=1|X_2=1)\cdot P(X_2 = 1|X_0=0)$$
$$=p_{11}\cdot p_{01}^{(2)}$$
$$=0.6 \cdot 0.26=0.156$$

### Q13.
Determine whether each of the following is stochastic matrix or not and why given that $s=\left\{1,2\right\}$? 

(a) $$A =\left[\begin{matrix}
&\frac{1}{2}		&\frac{1}{4}	&\frac{1}{4}		& \\
&1					&0				&0					& \\
\end{matrix}\right]$$

(b)$$B=
\left[\begin{matrix}
&\frac{15}{16}		&\frac{1}{16}	& \\
&\frac{2}{3}		&\frac{2}{3}	& \\
\end{matrix}\right]$$

(b)$$D=
\left[\begin{matrix}
&\frac{1}{2}		&-\frac{1}{2}	& \\
&\frac{1}{4}		&\frac{3}{4}	& \\
\end{matrix}\right]$$
#### Answer
##### part (a)
Since the matrix $A$ is not a square matrix, it is not a stochastic matrix.

##### part (b)
Since the $2^\text{nd}$ row $B$ does not sum up to $1$, it is not a stochastic matrix.

##### part (c)
Since $D_{12}$ is negative, it is not a stochastic matrix.
### Q14.
Given the transition matrix
$$P=
\left[\begin{matrix}
&0					&1				& \\
&1/2				&1/2			& \\
\end{matrix}\right]$$
and 
$$\pi^{(0)}=
\left[\begin{matrix}
&1/3				&2/3			&
\end{matrix}\right]$$

Find

(a) $\pi^{(3)}$ (b) $p^{(3)}_{21}$ (c) $\pi^{(3)}_2$

#### Answer
$$P^{(3)} = PPP$$
$$=
\left[\begin{matrix}
&0					&1				& \\
&1/2				&1/2			& \\
\end{matrix}\right]

\left[\begin{matrix}
&0					&1				& \\
&1/2				&1/2			& \\
\end{matrix}\right]

\left[\begin{matrix}
&0					&1				& \\
&1/2				&1/2			& \\
\end{matrix}\right]$$

$$=
\left[\begin{matrix}
&0					&1				& \\
&1/2				&1/2			& \\
\end{matrix}\right]

\left[\begin{matrix}
&1/2				&1/2				& \\
&1/4				&3/4			& \\
\end{matrix}\right]$$

$$=
\left[\begin{matrix}
&1/4				&3/4			& \\
&3/8				&5/8			& \\
\end{matrix}\right]$$

##### part (a)
$$\pi^{(3)}=\pi^{(0)}P^{(3)}$$
$$=
\left[\begin{matrix}
&1/3				&2/3				&
\end{matrix}\right]

\left[\begin{matrix}
&1/4				&3/4			& \\
&3/8				&5/8			& \\
\end{matrix}\right]$$
$$=
\left[\begin{matrix}
&1/3				&2/3				&
\end{matrix}\right]
$$
##### part (b)
$$p^{(3)}_{21}=3/8$$

##### part (c)
 $$\pi^{(3)}_2=2/3$$
 
### Q16.
Given the transition matrix
$$P=
\left[\begin{matrix}
&0					&0.5			&0.5			& \\
&0.5				&0.5			&0				& \\
&0					&1				&0				& \\
\end{matrix}\right]$$
And
$$\pi^{(0)}=
\left[\begin{matrix}
&\frac{2}{3}		&0				&\frac{1}{3}	& \\
\end{matrix}\right]$$
Find:
(a) $p^{(3)}_{32}$ (b) $p^{(2)}_{31}$ (c) $\pi^{(4)}$ (d) $\pi^{(4)}_{3}$

#### Answer
$$P^{(2)} = PP$$
$$=
\left[\begin{matrix}
&0					&0.5			&0.5			& \\
&0.5				&0.5			&0				& \\
&0					&1				&0				& \\
\end{matrix}\right]
	
\left[\begin{matrix}
&0					&0.5			&0.5			& \\
&0.5				&0.5			&0				& \\
&0					&1				&0				& \\
\end{matrix}\right]
$$
$$=
\left[\begin{matrix}
&0.25				&0.75			&0				& \\
&0.25				&0.5			&0.25			& \\
&0.5				&0.5			&0				& \\
\end{matrix}\right]
$$

$$P^{(3)} = PP^{(2)}$$
$$=
\left[\begin{matrix}
&0					&0.5			&0.5			& \\
&0.5				&0.5			&0				& \\
&0					&1				&0				& \\
\end{matrix}\right]
	
\left[\begin{matrix}
&0.25				&0.75			&0				& \\
&0.25				&0.5			&0.25			& \\
&0.5				&0.5			&0				& \\
\end{matrix}\right]
$$
$$=
\left[\begin{matrix}
&0.375				&0.5			&0.125			& \\
&0.25				&0.625			&0.125			& \\
&0.25				&0.5			&0.25			& \\
\end{matrix}\right]
$$

$$P^{(4)} = PP^{(3)}$$
$$=
\left[\begin{matrix}
&0					&0.5			&0.5			& \\
&0.5				&0.5			&0				& \\
&0					&1				&0				& \\
\end{matrix}\right]
	
\left[\begin{matrix}
&0.375				&0.5			&0.125			& \\
&0.25				&0.625			&0.125			& \\
&0.25				&0.5			&0.25			& \\
\end{matrix}\right]
$$
$$=
\left[\begin{matrix}
&0.25				&0.5625			&0.1875			& \\
&0.3125				&0.5625			&0.125			& \\
&0.25				&0.625			&0.125			& \\
\end{matrix}\right]
$$
##### part (a)
$$p^{(3)}_{32} = 0.5$$ 

##### part (b)
$$p^{(2)}_{31} = 0.5$$ 

##### part (c)
$$\pi^{(4)}=\left[\begin{matrix}
&0.25				&0.5833			&0.1667			& \\
\end{matrix}\right]$$

##### part (d)
$$\pi^{(4)}_3= 0.1667$$


### Q17. 
A salesman's area consists of three cities, $A, B\;\&\; C$. He never sells on the same city on successive days. If he sells in city $A$ then the next day he sells in city $B$. However, if he sells in either $B$ or $C$, then the next day he is twice as likely to sell in city $A$ as in the other city. Find
	
a) The transition matrix of this process.
b) In the long run, how often he sells in each of the cities.

#### Answer
##### part (a)
$$\therefore \;\; P=\left[\begin{matrix}
&0					&1				&0				& \\
&\frac{2}{3}		&0				&\frac{1}{3}	& \\
&\frac{2}{3}		&\frac{1}{3}	&0				& \\
\end{matrix}\right]$$
##### part (b)
$\hat{p} = \left[\begin{matrix} &x &y &z &\end{matrix}\right]$

$$\therefore \hat{p}P=\hat{p}$$

$$\therefore \;\; \left[\begin{matrix} &x &y &z &\end{matrix}\right] 
\left[\begin{matrix}
&0					&1				&0				& \\
&\frac{2}{3}		&0				&\frac{1}{3}	& \\
&\frac{2}{3}		&\frac{1}{3}	&0				& \\
\end{matrix}\right]

=\left[\begin{matrix} &x &y &z &\end{matrix}\right] $$

$$
\therefore \;\;\;\;
\begin{matrix}
&					&\frac{2}{3}y	&+\frac{2}{3}z	&= 	&x &..(i)\\
&x					&				&+\frac{1}{3}z	&= 	&y &..(ii)\\
&					&\frac{1}{3}y	&				&= 	&z &..(iii)\\
&x					&+y				&+z				&=	&1 &..(iv)\\
\end{matrix}
$$

from $(iii)$, 
$$y=3z$$

Substuting $y$ to $(i)$, 
$$2z + \frac{2}{3}z = x$$
$$\Rightarrow \frac{8}{3}z = x$$

Substuting $x, y$ to $(iv)$, 
$$\frac{8}{3}z + 3z + z = 1$$
$$\Rightarrow (8+9+3)z = 3$$
$$\Rightarrow z = \frac{3}{20} = 0.15$$

$$\therefore y = 3\cdot\frac{3}{20} = \frac{9}{20} = 0.45$$

$$\therefore x = \frac{8}{3}\cdot\frac{3}{20}=\frac{2}{5}=0.4$$

The stationary distribution

$$\hat{p}=\left[\begin{matrix} &0.15 &0.45 &0.4 &\end{matrix}\right]$$

Hence he sells in city $A$ $15\%$ of the time, city $B$ $45\%$ and city $C$ $40\%$ of the time. 

### Q18.
Consider the transition matrix $P$ of a markov chain $S=\left\{0,1\right\}$.
$$P=
\left[\begin{matrix}
&0.9				&0.1			& \\
&0.2				&0.8			& \\
\end{matrix}\right]$$

Given that $P(X_0=0)=P(X_0=1)=0.5$, 

a) Find the distribution of $X_n$
b) Find the distribution of $X_n$, when $n\rightarrow\infty$

#### Answer
##### part (a)
$$\pi^{(0)}=\left[\begin{matrix} &0.5 &0.5 &\end{matrix}\right]$$

$$\pi^{(1)} = \pi^{(0)}P = \left[\begin{matrix} &0.5 &0.5 &\end{matrix}\right]

\left[\begin{matrix}
&0.9				&0.1			& \\
&0.2				&0.8			& \\
\end{matrix}\right]

$$
$$
= \left[\begin{matrix} &0.5 \cdot 0.9 + 0.5 \cdot 0.2 
&0.5 \cdot 0.1 + 0.5 \cdot 0.8 &\end{matrix}\right]
$$
$$\Rightarrow \;\pi^{(1)}
= \left[\begin{matrix} &0.55 
&0.45 &\end{matrix}\right]
$$

##### part (b)
$$\hat{p}=\left[\begin{matrix} &x &y &\end{matrix}\right]$$

$$\therefore \hat{p}P=\hat{p}$$

$$\Rightarrow\; \left[\begin{matrix} &x &y &\end{matrix}\right] 

\left[\begin{matrix}
&0.9				&0.1			& \\
&0.2				&0.8			& \\
\end{matrix}\right]

=\left[\begin{matrix} &x &y &\end{matrix}\right] $$

From here we get the equations, 

$$
\begin{matrix}
&0.9x				&+0.2y			&= 	&x &..(i)\\
&0.1x				&+0.8y			&= 	&y &..(ii)\\
&x					&+y				&=	&1 &..(iii)\\
\end{matrix}
$$

from $(iii)$,

$$x=y-1$$

Substuting to $(ii)$,

$$0.1(1-y)=(1-0.8)y$$
$$\Rightarrow \; 0.1=0.2y+0.1y$$
$$\Rightarrow \; y=\frac{0.1}{0.3}=\frac{1}{3}$$

$$\therefore \;\; x = \frac{2}{3}$$

Hence the distribution $X_n$, when $n\rightarrow\infty$ is 
$$\hat{p}=\left[\begin{matrix} &\frac{1}{3} &\frac{2}{3} &\end{matrix}\right]$$