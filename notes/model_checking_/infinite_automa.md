$$
\newcommand{\infexts}{\stackrel{\infty}{\exists}}
\newcommand{\infforall}{\stackrel{\infty}{\forall}}
$$

# Infinite Automa

$\textbf{Definition}$ A *nondeterministic Buechi automaton* (NBA) is a tuple $\mathcal{A}=(Q,\Sigma,\delta,Q_0, F)$. A *run* of an NBA over an infinite word $\sigma=A_0A_1\dots A_n\dots$ is an infinite sequence $q_0q_1\dots q_n\dots$ of states of $\mathcal{A}$ such that 

$\mathcal{L}_\omega(\mathcal{A}) := \{ \sigma=A_0A_1\dots A_n\dots | \exists q_0q_1\dots q_n\dots s.t. q_0\in Q_0, \forall n\ge 0, q_{n+1}\in\delta(q_n, A_n) , \infexts n. q_n\in F \}$.

The witness $q_0q_1\dots q_n\dots$ of an infinite word $\sigma$ is a run over $\sigma$
