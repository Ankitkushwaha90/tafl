Turing Machines and Recursive Function Theory : Basic Turing Machine Model, Representation of
Turing Machines, Language Acceptability of Turing Machines, Techniques for Turing Machine
Construction, Modifications of Turing Machine, Turing Machine as Computer of Integer Functions,
Universal Turing machine, Linear Bounded Automata, Church’s Thesis, Recursive and Recursively
Enumerable language, Halting Problem, Post’s Correspondance Problem, Introduction to
Recursive Function Theory.

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

Turing Machines and Recursive Function Theory : Basic Turing Machine Model, Representation of
Turing Machines, Language Acceptability of Turing Machines, Techniques for Turing Machine
Construction, Modifications of Turing Machine, Turing Machine as Computer of Integer Functions,
Universal Turing machine, Linear Bounded Automata, Church’s Thesis, Recursive and Recursively
Enumerable language, Halting Problem, Post’s Correspondance Problem, Introduction to
Recursive Function Theory.
Turing Machines and Recursive Function Theory
1. Basic Turing Machine Model
1.1 Definition
A Turing Machine (TM) is a mathematical model of computation that defines an abstract machine capable of simulating any algorithmic process. It consists of:

M = (Q, Σ, Γ, δ, q₀, B, F)

Q: Finite set of states.

Σ: Input alphabet (finite set of symbols).

Γ: Tape alphabet (finite set of symbols, Σ ⊆ Γ).

δ: Transition function:

δ: Q × Γ → Q × Γ × {L, R}

q₀: Initial state (q₀ ∈ Q).

B: Blank symbol (B ∈ Γ, B ∉ Σ).

F: Set of accepting/final states (F ⊆ Q).

1.2 Components
Infinite Tape: Divided into cells, each containing a symbol from Γ.

Tape Head: Reads/writes symbols and moves left (L) or right (R).

Control Unit: Governs the TM's behavior based on the current state and symbol under the tape head.

1.3 Operation
Start in state q₀ with the input written on the tape.

Repeatedly apply the transition function δ until a final state is reached or no transition is defined.

If the TM halts in an accepting state, the input is accepted; otherwise, it is rejected.

2. Representation of Turing Machines
2.1 Transition Diagrams
States are represented as circles.

Transitions are represented as arrows labeled with the input symbol, symbol to write, and direction (L/R).

Example:
TM for L = {0ⁿ1ⁿ | n ≥ 1}:

States: q₀, q₁, q₂, q₃, q₄

Transitions:

δ(q₀, 0) = (q₁, X, R)

δ(q₁, 0) = (q₁, 0, R)

δ(q₁, 1) = (q₂, Y, L)

δ(q₂, Y) = (q₂, Y, L)

δ(q₂, 0) = (q₃, 0, L)

δ(q₃, X) = (q₀, X, R)

δ(q₀, Y) = (q₄, Y, R)

2.2 Transition Tables
A table listing the current state, input symbol, next state, symbol to write, and direction.

Example:
Current State	Input Symbol	Next State	Write Symbol	Direction
q₀	0	q₁	X	R
q₁	0	q₁	0	R
q₁	1	q₂	Y	L
3. Language Acceptability of Turing Machines
A TM accepts a language L if it halts in an accepting state for every input w ∈ L.

A TM rejects a language L if it halts in a non-accepting state or loops indefinitely for every input w ∉ L.

4. Techniques for Turing Machine Construction
Marking Symbols: Use special symbols to mark positions on the tape.

Multiple Tracks: Simulate multiple tapes using a single tape with multiple tracks.

Subroutines: Use modular design to break the TM into smaller, reusable components.

5. Modifications of Turing Machines
Multi-Tape TM: Multiple tapes with independent heads.

Non-Deterministic TM: Multiple possible transitions for a given state and symbol.

Multi-Dimensional TM: Tape extends infinitely in multiple dimensions.

6. Turing Machine as Computer of Integer Functions
A TM can compute integer functions by encoding inputs and outputs as strings on the tape.

Example: A TM to compute f(x) = x + 1:

Input: x represented as a string of 1s.

Output: x + 1 represented as an additional 1.

7. Universal Turing Machine
A Universal Turing Machine (UTM) can simulate any other TM given its description and input.

It is the theoretical foundation for modern computers.

8. Linear Bounded Automata (LBA)
An LBA is a restricted TM where the tape is bounded by the length of the input.

LBAs recognize context-sensitive languages.

9. Church’s Thesis
Church-Turing Thesis: Any function that can be computed by an algorithm can be computed by a Turing Machine.

It is a hypothesis, not a theorem, but widely accepted in computer science.

10. Recursive and Recursively Enumerable Languages
Recursive Language: A language L is recursive if there exists a TM that halts on all inputs and accepts w ∈ L while rejecting w ∉ L.

Recursively Enumerable Language: A language L is recursively enumerable if there exists a TM that halts and accepts w ∈ L but may not halt for w ∉ L.

11. Halting Problem
The Halting Problem is the problem of determining, given a TM and an input, whether the TM will halt on that input.

It is undecidable: No algorithm can solve it for all possible inputs.

12. Post’s Correspondence Problem (PCP)
PCP is an undecidable problem that asks, given a set of dominoes with strings on top and bottom, whether there exists a sequence of dominoes where the concatenated top strings equal the concatenated bottom strings.

13. Introduction to Recursive Function Theory
Recursive Function Theory studies the class of functions that can be computed by TMs or other equivalent models.

Key concepts include:

Primitive Recursive Functions: Basic functions (e.g., addition, multiplication) built from simpler functions.

μ-Recursive Functions: Functions defined using minimization.

Conclusion
Turing Machines are a foundational model of computation, capable of simulating any algorithmic process. Key concepts include language acceptability, modifications of TMs, the Universal Turing Machine, and undecidable problems like the Halting Problem and Post’s Correspondence Problem. Recursive Function Theory provides a mathematical framework for understanding computability. These concepts are essential for theoretical computer science and the study of algorithms.
