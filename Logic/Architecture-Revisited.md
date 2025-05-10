Returning to this project after many years of thinking through similar ideas from different perspectives, my ideas about architecture have `advanced'.
Most of this just a maturing of my own ideas, but the changing context, in which Artificial Intelligence has itself moved forward at an accelerating pace, enables me to to take a different stance on some crucial issues.

This new architectural stance reflects three aspects of the present state of the art.
The first is the emergent capabilities of Large Language Models (LLMs), whose linguistic capabilities make it possible for me to contemplate core architectural features which are more cleanly divorced from concrete syntax in the expectation that LLMs will provide access to their content tailored to clients (man or machine) of diverse capabilities and needs.

A second aspect of the current state of the art which I consider important for this enterprise and which greatly influences the architecture is the continuing success of some elements of approaches to AI which predate the LLM, particularly evident in the work of the (original, London) Google Deepmind team, and perhaps most clearly exemplified by their Alpha-zero.

The salient features of this for present purposes are:
- hard coded rules creating a "perfect information" problem space.
- hard coded Monte Carlo Tree Search (MCTS) searched using heuristics from neural nets trained by reinforcement learning.
- instead of learning from masses of data, learning is accomplished by independent exploration of the problem space, in the case of games, by the software playing many games against itself.

A further possibility which I am now incorporating into the architecture derives from the idea of a singularity, which I have refined and elaborated to feature in all three major components in the StarDust constellation.

- [The Knowledge Base](The-Knowledge-Base)
- [A Deductive Engine](A-Deductive-Engine)
