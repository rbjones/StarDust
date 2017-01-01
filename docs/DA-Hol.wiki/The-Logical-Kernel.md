
### The Logical Kernel

The logical kernel is designed to achieve the following effects:

- abstraction from concrete representations (this results from structuring of the context/theory representation and use of abstract rather than concrete syntax except on end-user interfaces)  
- Computational efficiency to support _caclulemus_ like functionality, i.e. efficient execution of calculable functions  
- full logical metalanguage allows intelligent assistants to understand high level proofs  

Here are some features we envisage in such a logical kernel.

-  the kernel will be follow an augmented LCF paradigm, i.e.:  
    * the logical kernel provides inference functions which implement a fixed set of derived rules in the HOL logic.
    * high level presentations of proof computations may be provided using a functional metalanguage

-  those features are augmented in the following ways:  
    * a derived rule is available which effectively evaluates efficiently an executable part if the HOL object language
    * the metalanguage is also HOL and is used in high level descriptions of proofs
    * theorem proving takes place in two logical contexts at once, an object context and a meta-context.
The meta context contains the definitions of all the high-level proof capabilities used in a proof, and the high level proof can therefore be preserved to admit re-validation of proofs after their initial construction.

