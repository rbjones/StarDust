
### Deductive Smart Contracts

When considering the potential for some new technology it is common to ask "What is the killer application?".

I have thought about the long term prospects for proof technology for many years, and for most of that time I have considered that the "killer app" was design automation.
Ultimately, once AI advanced far enough, we would not need to implement a design (and hope to formally verify that it met the requirements).
We would write a specification of the required system, and the machine (possibly with a bit of help and guidance) would construct a formally verified solution.

This is a part of the ambition for this project, but of course, its a long way down the track, and I now believe that there are possible killer applications which are simpler and closer.

Proof is about trust.
Trust is achieved partly from using simple languages with precisely defined semantics, relative to which formal proof rules can be unambiguously prescribed which enable true sentences to be established conclusively.

We are moving into a world in which business processes are automated through so-called `smart contracts'.
There is a lot of hype around crypto-currencies and distributed ledgers at present, and I am myself a qualified skeptic about whether smart contract is a proper name for this kind of process automation, and whether these contracts should be implemented on public blockchains.
I am not sceptical about the more general idea that business processes, including of course asset transfers, will be increasingly automated.

When business processes are automated, whether by block-chain resident smart contracts or by some other means, the steps in the process will often be triggered by events in the real world, information about which is injected into the system by `oracles'.
An oracle is some device or person which feeds in a fact about some state of the world or some event which has happened.
If contract or business process involves very complex real world activities, then when formally specified a stage in the process may be completed by a very complex combination of events reported by such oracles.
If the contract is formally specified in some language which is essentially syntax over abstract HOL, then the completion of the stage will be deducible from the reports of the relevant oracles.

The normal conception of 'smart contract' is algorithmic, and like all algorithms these may be inscrutable.
A high-level declarative specification of such a `contract' could be written using some approprate notation embedded into HOL, and the inference from the oracular inputs to the completion of some stage in the contracct would be relatively simple and easily automated.

Though initial applications might be simple, the placement of this capability in the context of a deductive cloud pvaes the way for more complex processes to be specified and automated, involving more sophisticated inferences from the mass of information in the relevant parts of the cloud.











