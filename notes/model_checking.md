# Model Checking

Model checking models a system as a transition system and automatically checks properties on this transition system.

A transition system has (finite, coutably infinte or uncountably infinite) states and actions from states to states.
All states are abelled with atomic propositions (atomic since taken for granted), and some states are specified as initial states.

The transition system models the transitional nature of a system and is equavalent to the directed graph, a mathematical structure that makes automation possible, unlike Turing machine.

[comment]: #(The directed graph captures the static nature of the system i.e. its structure. With the concept of time endowing the system, its behaviour i.e. the set of all possible transition sequences captures its dynamic nature. The time concept implies nondeterminism, since a system with determined behaviour is inherently stateless and timeless and thus trivial. The system will take one of the transitions nondeterministicly from its present state.A tree represents all possiblities of a system, as time goes new possible branches diverge. A directed graph represents all potential possibilities of a system, with the structure of system as mastered knowledge and folding repetitive possiblities/states based on that knowledge. A line represents a timeless system, which has only one possibility. The concept of timeness is ubiquitous: Hamiltonian mechanics, Lagrangian mechanics, Newton (classical) mechanics; operational programming, functional (no side-effect) programming)

Finite automa i.e. DFA and NFA can be viewed as a special instantialization of the transition system of finiteness, unlabelled states, initial and final states, and uses its actions to recognizing a language.
Transition system can be viewed as an abstraction of finite automa conversely. The nondeterminism of automa is different from the nondeterminism of transition system, since the input string of symbols eliminates the nondeterminism of DFA and retains NFA a stronger sense of nondeterminism. In this way, an automa is more likely to specify a property than be specified by a property. DFA, NFA and regular language have the same expressiveness
 
digital circuit / combinational logic
finite state machine / regular grammar
pushdown automaton / context-free grammar
turing machine

Model checking uses transition system to check whether the system satisfies certain properties. We need define a specification formalism to express the properties and the associated verification algorithm to perform the check.

We name the state sequence as path, act sequence as execution, lable (atomic proposition) sequence as trace. The state is conceptually more internal with lable more external i.e. more observabel. We often specify properties of system via specifying one of path, execution or trace.

The verification algorithm is basically traversing all possibilities i.e. DFS or BFS algorithm on the directed graph of transform system. Beyond traversing, we still need automated method to check whether the property is satisfied in one state.

One general formalism is linear time property, which specify the of traces the system should exhibit within.

$\textbf{Definition}$ A *linear time property* (LT property) over the set of atomic propositions $AP$ is a subset of $\Sigma^\omega$ where $\Sigma :=(2^{AP})$. 
$\Sigma^\omega$ is the set of infinite sequences (formally, infinite words) $a_0a_1\dots a_n\dots$ s.t. $\forall n,a_n\in\Sigma$. 
A transition system $\TS$ *satisfies* a linear-time property $P$, written as $TS\models P$, if $Traces(TS)\subseteq P$.

Dividing linear time property more finely leads to the safety property, which refute finite behaviour, and liveness property, which refute infinite behaviour. Any linear time property can be expressed as a conjunction of them.

The transition system is often nondeterministic, and thus uses fairness assumption to resolve the determinism and rule out unrealistic behavior.

More concretely, safety properties can be characterized by finite words (finite bad prefixes) which can be encoded by finite automata while liveness proeperties can be characterized by infinite word (infinite bad sequences), which can be encoded by [infinite automa](/model_checking/infinite_automa) i.e. $\omega$-automa.