https://2025.pycon.it/en/event/logfire-ai

Speaker: [Marcelo Trylesinski](https://www.linkedin.com/in/marcelotryle)

[PydanticAI](https://ai.pydantic.dev/)

[Logfire](https://pydantic.dev/logfire)

---

tool -> pass context to the model
tool_plain -> no context

logfire -> on top of opentelemetry

The name of the tool is important since it tells the LLM what the tool does.
You can also use the docstring of the function to describe the tool.

tavily -> search tool
mcp -> playwright tools


https://ai.pydantic.dev/evals/

Define a case (input, expected output) and the evaluators (such as LLM judge)

Create a dataset and then dataset.evaluate_sync(your_agent)