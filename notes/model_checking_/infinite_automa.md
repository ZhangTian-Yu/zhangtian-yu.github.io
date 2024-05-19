# Infinite Automa

A *nondeterministic Buechi automaton* (NBA) is a tuple $\mathcal{A}=(Q,\Sigma,\delta,Q_0, F\subseteq Q)$. 
The language a NBA accepts is

$\mathcal{L}_\omega(\mathcal{A}) := \{ \sigma=A_0A_1\dots A_n\dots \mid \exists q_0q_1\dots q_n\dots s.t. q_0\in Q_0, \forall n\ge 0, q_{n+1}\in\delta(q_n, A_n) , \stackrel{\infty}{\exists} n. q_n\in F \}$

The witness $q_0q_1\dots q_n\dots$ of an infinite word $\sigma$ is called a run over $\sigma$

A *generalized nondeterministic Buechi automaton* (GNBA) is a tuple $\mathcal{A}=(Q,\Sigma,\delta,Q_0, \mathcal{F}\subseteq 2^Q)$. 
The language a NBA accepts is

$\mathcal{L}_\omega(\mathcal{A}) := \{ \sigma=A_0A_1\dots A_n\dots \mid \exists q_0q_1\dots q_n\dots s.t. q_0\in Q_0, \forall n\ge 0, q_{n+1}\in\delta(q_n, A_n) , \forall F\in\mathcal{F}\stackrel{\infty}{\exists} n. q_n\in F \}$

GNBA and NBA are equivalent i.e. have the same expressive power. Reduction from NBA to GNBA is trivial. The other direction is given a construtive proof:

$\forall$ GNBA $\mathcal{G}$ $\exists$ NBA $\mathcal{A}$ s.t. $L_\omega(\mathcal{G})=L_\omega(\mathcal{A})$.

Let $\mathcal{G}=(Q,\Sigma,\delta,Q_0,\mathcal{F})$ be a GNBA. 
If $\mathcal{F} = \emptyset$, $L_\omega(\mathcal{G})$ is the set of all infinite words that admit an infinite run, recognized by an NBA reducing from the GNBA by  setting every state in $Q$ as a final state. 

Let $\mathcal{F}=\{F_0,\dots,F_{k-1}\}$ with $k\ge 1$. Then an NBA $\mathcal{G}=(Q',\Sigma,\delta',Q'_0,F')$ that recognizes $L(\mathcal{G})$ takes a round-robin fashion to visit $F_0,\dots, F_{k-1}$ in order.

* $Q':=Q\times \{0,1,\dots,k-1\}$;
* $Q'_0:=Q_0\times\{0\}$;
* $F':=F_0\times\{0\}$;
* $\delta'((q,j),A):= \{(q',j)\mid q'\in\delta(q,A)\}$ if $q\not\in F_j$, and $\delta'((q,j),A):= \{(q',{(j+1)}{\mod{}}{k})\mid q'\in\delta(q,A)\}$ otherwise.