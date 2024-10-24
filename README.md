# LLM-Oriented Programming (LOP)

I’ve discussed a new programming paradigm called **LLM-Oriented Programming (LOP)** in a few small groups, and it’s generated a lot of interest. The reality is, in the near future, companies will either have Large Language Models (LLMs) contributing 90% of their codebase, or they’ll be out-competed by those that do.

In the pre-LLM era, the goal of writing clean code, naming functions/parameters thoughtfully, and providing well-documented code was to ensure that your teammates (and your future self) could read and understand the work without getting lost—and maybe even be inspired by it. But now, the goal has shifted. You’re developing for LLMs.

This means **all text content related to an API endpoint should be structured in a way that can be easily retrieved and appended to a prompt**. Here are some practices I’ve found useful:

- **Think of it as an instruction manual, not just documentation**. Be direct and concise. List explicit do’s and don’ts. Share your thought process and explain any internal terms.

- **Avoid cross-referencing**. For example, if two functions share a similar set of parameters, don’t write: “These arguments are the same as in `foo()`.” Unless you’ve built a sophisticated retrieval system, LLMs won’t see the argument definitions and will have to guess (or hallucinate).

- **Use embedding distance tests** to see how distinct your function/method names are from each other and how well their corresponding documents reflect those differences. This helps improve accuracy when LLMs retrieve related information.

- **Provide more examples than you would for human readers**. Even complicated code snippets work well here—LLMs can handle them and learn a lot from them. 

- **Run LLM-based tests**. Ask LLMs to complete tasks using your API and documentation, then assert the generated code. You can either have the LLM judge the correctness or assert the execution results. This is far more engaging than unit tests, and you’ll get hooked. I think there’s space here for new testing frameworks to emerge.

- **Create meta-learning structures**. Beyond simple docstrings for each function, write down the design patterns and higher-order reasoning behind your code. Chances are, you already have this figured out, but be sure to convert visual aids (like architecture diagrams) into text. While all LLMs are moving toward multimodality, and some (like the new Cloude 3.5) have learned ["computer user"](https://docs.anthropic.com/en/docs/build-with-claude/computer-use), text remains much easier to work with in automation.

I will keep adding new learnings here. PR's welcomed. 
