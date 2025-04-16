The principal features here are:

* Full support for formal derivation and application of "classical" mathematics, either in the _abstract_ simple type theory (STT) or in Higher Order Set theory (HOST), via STT with a strong axiom of infinity (or an axiomatic Higher Order Set Theory).
Congenial concrete presentations of mathematical syntax do not belong to the abstract core.

* To achieve computational efficiency HOL will be both the object language and the meta-language, and the logical kernels (there may be more than one) may evaluate computable expressions in either the meta- or the object-language as part of the proof/computation process.

* If more exotic type systems, classical or constructive, are desired, it is recommended that embeddings are used, 
though, since there is no native concrete syntax, such embedded concrete languages are at a par with HOL itself.

 
I think of DA-Hol as a 21st Century sequel to the QED project, though the proposal is much broader in scope. I do therefore regard it as a core requirement that good support for mathematics is provided.

However, my own sense of priorities in this may be quite different to that of some, or perhaps even many other QED protagonists, so I will clarify this here, and spell out the consequences these differences have for the core technologies proposed.

Though keen to support mathematics, I am more interested in the applications of mathematics than I am in its further development. I am of the opinion that engineers are more likely to make significant use of proof technology than academic mathematicians who further develop mathematical theories. Furthermore, I believe that even for pure mathematicians, proof technologies will only be adopted when then make it possible to achieve results which could not have been achieved without them, and that they will then be transforming the way mathematical theories are developed, not providing perfect support for continuing to do mathematics in the way that it has always been done (and of course, there is no such way, the practice of mathematics has continuously evolved, sometimes faster, sometimes slower).

It is very hard to anticipate what kinds of foundation system, if any, may ultimately find favour among this kind of professional mathematician. Most of them aren't really interested, some of them think they don't need a foundation at all, much less a formal one, and when foundational ideas become relatively fashionable among mathematicians, they are likely (as, I suggest, in the case of HOTT), to be even less acceptable to the majority of mathematicians as a working environment than the traditional ones which they have been happy to mostly ignore.

We have no time to debate foundations, there is an opportunity in the state of Machine Learning today to achieve a step function in the proficiency of machine mathematics and we should seize the initiative today with what we have.
This sentiment is I think underpinned by the enduring popularity of Mike Gordan's HOL, despite three decades of debate about the merits of the simple type system.
