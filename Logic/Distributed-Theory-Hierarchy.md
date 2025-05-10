In HoLoTruth we use [_abstract HOL_ as a "universal" representation for knowledge](HOL for Knowledge Representation).

Here we sketch some of the key aspects of how that works.

The deductive cloud comes in two principal ways:

* [Native](#native)
    - [Logical Contexts](#logical-contexts)
    - [Abstract Theories](#abstract-theories)
    - [Concrete Theories](#concrete-theories)
* [Non-native](#non-native)
    - [Static](#static)
    - [Dynamic](#dynamic)

#### Native
##### [Logical Contexts](Logical-Contexts)

All knowledge representation is to be done in languages obtained by extension of the core abstract HOL language.
These abstract languages are defined by structures which are called "logical contexts", whose role is to define a HOL signature, and to constrain (define) the names in that signature. 
In the distributed deductive cloud, each logical context has a Universal Resource Identifier and a new context would be represented by a file which refers to the context or contexts which it extends or combines using the URI for that context including a hash of the definition of the context, and digitally signed by the agent which created the context.
This is a pattern which is repeated for all the resources in the deductive cloud.
Resources are new files with an associated URI (often a URL) which extend by reference using URI and hash of the resources being extended supplemented by the details of the extension, the whole signed by the creating authority.

Because the internal language is abstract, the contexts are spartan.
The abstract language is extended by adding new vocabulary, and the new vocabulary is given meaning by some _constraint_ which is a sentence in HOL which will be true only if the values of the new names are as required.
Often this will be a _definition_, but sometimes the constraint will not wholly determine the values of the new names.
These constraints are usually _conservative_.

##### Abstract Theories

When new results are deduced, these are saved in the deductive cloud as _theories_.
A theory consists of three main parts.
It has references to two logical contexts, and it provides a number of judgements which detail the results of the deductions, viz: certain new theorems together with information about how these theorems were obtained.
The two logical contexts required are a context for the object language in which the proven theorem is expressed, and one for the meta-theory containing the necessary vocabulary for a high-level description of the proof of the theorem, or of other meta-theoretic results which are held in the theory.

As in LCF systems generally the language in which proofs are expressed is extensible, and as theories are developed the vocabulary used to describe proofs is often extended as well.
In this case this language is an abstract HOL language, but as with all other uses of abstract HOL, the concrete presentation may be chosen to suit the users of the system.

##### Concrete Theories

A concrete theory is a theory together with information describing how that theory may be presented to agents which require something more concrete than the abstract structures, typically people, and which facilitates the entry of extensions (of contexts or theories).
Once again, HOL is used to define the concrete presentations, and a context is needed which provides the necessary vocabulary for defining the concrete presentation, this is a kind of meta-context and may itself come as a concrete theory.

#### Non-native

DA-Hol is not intended only to support deduction in small logical enclaves of the cloud.
It is intended to provide a framework for reasoning deductively about anything which can be found in "the cloud".
Of course, it is easier to provide sound reasoning within some context if the system has constructed the context with that in mind.
However, a variety of methods can be deployed which will permit reasoning in contexts which include information which has not been curated by DA-Hol.

The problem is particularly difficult for data sources which are dynamic, for if treated naively these will be prolific sources of contradictions, so we sketch here some possible approaches to each of these broad categories in turn.

##### Static  

There are two distinct classes of method which can be used to reason about static data in the cloud.
These both depend on a formal semantics for the data in question.
In the first case this is given in the meta-language, and results in the alien data source being defined as an alternative concrete syntax for HOL.
In the second case the data is treated as a HOL data value, possibly a finite sequence of characters, and a function is defined in HOL which maps values of this kind into whatever values or propositions best represent then in the appropriate HOL contexts.

Thus, for example, a table with two columns, one a social security number, the second an age, might be imported into a HOL context in which there is a predicate A(n,y) which means "the person whose social security number is n has age y years", using a function which maps a table of two such columns to the conjunction of the set of predicates A(n,m) for all values n and m which occur together in some row of the table.  
A context can be created which imports a non-native data source into a DA-Hol context by treating the data source as concrete syntax for a new language whose abstract syntax is rendered in abstract HOL.

This involves defining in a meta-context (using HOL) the concrete syntax of the language, how this maps to its abstract syntax, and how the abstract syntax of the language is represented as HOL.
Thus would typically revolve around defining in HOL new constants which correspond to the constructors in the abstract syntax and capture the semantics of that kind of structure in the language.
This the classic pattern for a "shallow" semantic embedding.  

Once that is done, the data can be imported to create a matching HOL context.

##### Dynamic

The problems arising from non-monotonicity of changes in the premise set for deductive inference has been widely discussed in the AI community, and is often thought to require the use of "non-monotonic logic".
DA-Hol itself is founded in a monotonic logic, but the universality of this logical system means that any coherent logical system with a definite semantics will be interpretable in abstract HOL and may therefore be used as a concrete presentation for an idiolect of HOL.
The use of such non-monotonic languages may provide an effective way to deal with data from dynamic external contexts, but we also have a number of ideas for methods which may be used without adopting a non-monotonic language.















