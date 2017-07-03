
### Language and Logic

We are concerned here exclusively with _propositional_ language and _deductive_ logic.

[Propositional Language](#propositional-language)  
[Deductive Logic](#deductive-logic)  
[Logical Consistency and Completeness](#logical-consistency-and-completeness)  
[Interpretation and Proof Theoretic Strength](#interpretation-and-proof-theoretic-strength)  
[Translation and Expressiveness](#translation-and-expressiveness)  
[The Universality of HOL](#the-universality-of-HOL)  
[Practical Considerations](#practical-considerations)  

#### Propositional Language

Propositional language is language in which one can express or assert sentences.
A sentence is an expression which has a truth value.
The elements of the language have meanings which combine to give meaning to the sentences of the language, and the meaning of a sentence consists of, or includes, its truth conditions.
If you understand the meaning, and hence the truth conditions, of a sentence, then when you are told its truth value, you know something about the subject matter of the sentence.
You know that the conditions necessary for the truth of the sentence hold.

So that's a thumbnail sketch of what propositional language is.

#### Deductive Logic

A logic is a set of rules which allow inference from a group of sentences in some language to a new sentence.
If the logic is sound, then these rules correspond to the meanings of the sentences of the language in the following way: the rules preserve truth.
This means that whenever the rules permit drawing some conclusion C from a set of premises S, then if all the sentences in S are true, then C will also be true.
Put another way, in a sound logic the rules only admit inference from S to C if whenever the truth conditions for all the sentences in S are satisfied, then so will be the truth conditions for C, in more jargon, the conjunction of the truth conditions for the sentences in S entails the truth condition for C.

Some kinds of logic are not sound in this way, though there may be controversy about whether these systems really should be accepted as _logic_s.
An example is _inductive_ logic.

#### Logical Consistency and Completeness

Sometimes the proof rules for some system allow any sentence to be derived, and the logic is then considered to be _inconsistent_, otherwise the logic is consistent.
One way to establish consistency is by ensuring that the language has a clearly defined semantics (i.e. the truth conditions of the sentences are well defined) and then proving that there is at least one sentence which is false under that semantics (i.e. its truth conditions are never satisfied) and that the logic is sound.
This establishes that no falsehood is derivable and the logic is consistent.

Most logical systems in use are consistent, though there have been many cases in which logical systems once thought consistent were found to be inconsistent.

A logical system is _complete_ if all true sentences of the language are derivable according to the rules of the logic.
Kurt Godel proved the incompleteness of all (effective) logical systems which contain arithmetic, and this applies to most of the languages of interest here.
We therefore have to settle for logical systems in which only some of the logical truths can be proven, and it is a matter of interest in a logical system how many of the truths expressible in the language can be proven in the logic.
Similar considerations apply also to the semantic expressiveness of a language.
It might be (and it always will be) that a language is complete only because it is limited in what truths it can express.

These considerations bear upon the claim I have made about "universality of HOL", upon what that claim means, and whether it can be established.

#### Interpretation and Proof Theoretic Strength

#### Translation and Expressiveness

#### Practical Considerations

