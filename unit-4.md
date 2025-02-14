Push Down Automata and Properties of Context Free Languages: Nondeterministic Pushdown
Automata (NPDA)- Definition, Moves, A Language Accepted by NPDA, Deterministic Pushdown
Automata(DPDA) and Deterministic Context free Languages(DCFL), Pushdown Automata for
Context Free Languages, Context Free grammars for Pushdown Automata, Two stack Pushdown
Automata, Pumping Lemma for CFL, Closure properties of CFL, Decision Problems of CFL,
Programming problems based on the properties of CFLs.


Pushdown Automata and Properties of Context-Free Languages
1. Nondeterministic Pushdown Automata (NPDA)
1.1 Definition
A Nondeterministic Pushdown Automaton (NPDA) is a 7-tuple:

M = (Q, Σ, Γ, δ, q₀, Z₀, F)

Q: Finite set of states.

Σ: Input alphabet (finite set of terminals).

Γ: Stack alphabet (finite set of stack symbols).

δ: Transition function:

δ: Q × (Σ ∪ {ε}) × Γ → Set of finite subsets of Q × Γ*

q₀: Initial state (q₀ ∈ Q).

Z₀: Initial stack symbol (Z₀ ∈ Γ).

F: Set of accepting states (F ⊆ Q).

1.2 Moves
An NPDA transitions based on:

Current state.

Input symbol (or ε).

Top stack symbol.

The transition function δ defines the possible moves:

δ(q, a, Z) = {(p₁, γ₁), (p₂, γ₂), ...}

From state q, on input a and stack top Z, the NPDA can move to state p₁ and replace Z with γ₁, or move to state p₂ and replace Z with γ₂, etc.

1.3 Language Accepted by NPDA
An NPDA accepts a string if:

The entire input is consumed.

The NPDA reaches an accepting state (final state acceptance) or the stack is empty (empty stack acceptance).

Example:
NPDA for the language L = {aⁿbⁿ | n ≥ 1}:

States: q₀, q₁, q₂

Transitions:

δ(q₀, a, Z₀) = {(q₁, AZ₀)}

δ(q₁, a, A) = {(q₁, AA)}

δ(q₁, b, A) = {(q₂, ε)}

δ(q₂, b, A) = {(q₂, ε)}

δ(q₂, ε, Z₀) = {(q₂, ε)}

2. Deterministic Pushdown Automata (DPDA) and Deterministic Context-Free Languages (DCFL)
2.1 Deterministic Pushdown Automata (DPDA)
A DPDA is a restricted form of NPDA where:

For every state, input symbol, and stack symbol, there is at most one transition.

ε-transitions are allowed only if no other transition is possible.

2.2 Deterministic Context-Free Languages (DCFL)
A language is DCFL if it is accepted by a DPDA.

DCFLs are a proper subset of CFLs.

Example: L = {aⁿbⁿ | n ≥ 1} is a DCFL.

3. Pushdown Automata for Context-Free Languages
Equivalence of CFG and NPDA:
For every CFG, there exists an NPDA that accepts the same language, and vice versa.

3.1 Construction of NPDA from CFG
Push the start symbol S onto the stack.

For each production rule A → α, add transitions to replace A with α on the stack.

For each terminal a, add transitions to pop a from the stack when a is read from the input.

Example:
CFG for L = {aⁿbⁿ | n ≥ 1}:

S → aSb | ab

NPDA Construction:

Push S onto the stack.

Use transitions to replace S with aSb or ab.

Pop a and b as they are read from the input.

4. Context-Free Grammars for Pushdown Automata
Given an NPDA, construct a CFG that generates the same language.

The construction involves creating variables for each state and stack symbol combination.

5. Two-Stack Pushdown Automata
A two-stack PDA is a more powerful automaton with two stacks.

It can recognize languages beyond CFLs, such as context-sensitive languages.

6. Pumping Lemma for Context-Free Languages
The Pumping Lemma for CFLs is used to prove that a language is not context-free.

6.1 Statement
For any CFL L, there exists a constant p (pumping length) such that any string s ∈ L with |s| ≥ p can be divided into five parts:

s = uvxyz

|vxy| ≤ p

|vy| > 0

For all i ≥ 0, uvⁱxyⁱz ∈ L

6.2 Application
To prove a language L is not context-free:

Assume L is context-free.

Choose a string s ∈ L with |s| ≥ p.

Show that no division s = uvxyz satisfies the Pumping Lemma conditions.

Conclude that L is not context-free.

Example:
Prove that L = {aⁿbⁿcⁿ | n ≥ 1} is not context-free:

Choose s = aᵖbᵖcᵖ.

Any division s = uvxyz will result in unequal numbers of as, bs, or cs when pumped.

7. Closure Properties of CFLs
CFLs are closed under:

Union: If L₁ and L₂ are CFLs, then L₁ ∪ L₂ is a CFL.

Concatenation: If L₁ and L₂ are CFLs, then L₁L₂ is a CFL.

Kleene Star: If L is a CFL, then L* is a CFL.

Homomorphism: If L is a CFL, then h(L) is a CFL.

CFLs are not closed under:

Intersection: The intersection of two CFLs may not be a CFL.

Complement: The complement of a CFL may not be a CFL.

8. Decision Problems of CFLs
Membership: Given a string w and a CFL L, is w ∈ L? (Decidable using CYK algorithm).

Emptiness: Is L empty? (Decidable).

Finiteness: Is L finite? (Decidable).

Equivalence: Given two CFLs L₁ and L₂, is L₁ = L₂? (Undecidable).

9. Programming Problems Based on CFLs
Implement an NPDA:

Simulate an NPDA for a given CFL.

Check membership using CYK algorithm:

Implement the CYK algorithm to check if a string is in a CFL.

Convert CFG to CNF:

Write a program to convert a CFG into Chomsky Normal Form.

Implement the Pumping Lemma:

Write a program to test if a language is context-free using the Pumping Lemma.

Conclusion
Pushdown automata (both NPDA and DPDA) are fundamental for recognizing context-free languages. Key concepts include the equivalence of CFGs and NPDAs, the Pumping Lemma for CFLs, and closure properties. These concepts are essential for solving programming problems and understanding the theoretical limits of context-free languages.
