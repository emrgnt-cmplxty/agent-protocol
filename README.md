# Agent Protocol
This protocol defines an interface for interacting with your agent.

The protocol is **tech stack agnostic**. Any agent can adopt this protocol no matter what framework they're using (or not using).

Because this protocol is open-source, any platform can adopt it and your agent then becomes automatically compatible with it.

We are starting with a minimal protocol and we want to build upon that iteratively by learning from agent developers about what they need - the agent space is young and we don’t want to build on wrong assumptions by defining a complex protocol from the start.

## Why adopt this protocol?
- The protocol will allow people to immediately start using benchmarks with their agents
- We can have general devtools (for development, deployment and monitoring) that can be built on top of this protocol
- You won’t need to write boilerplate API and you can focus on developing your agent
- Other people can more easily use and integrate with your agent

## How does the protocol work?
Right now the protocol is defined as a REST API (via the [OpenAPI spec](./openapi.yml)) with two essential routes for interaction with your agent:
- `POST /agent/tasks` for creating a new task for the agent (for example giving AutoGPT an objective that you want to accomplish)
- `POST /agent/tasks/{task_id}/steps` for executing one step of the defined task

We found out that a lot of agents are structured into “steps” – usually these steps are either iterations of the core agent loop or just parts of the code with a call to the LLM. These steps are non-deterministic and you want to have control over them when developing, testing, and controlling your agent.

> We plan to add a GraphQL support in the future.

### 💬 Public discourse & development
- PRs and issues are welcome!
- Join our [Discord](https://discord.gg/U7KEcGErtQ) and the [`agent-protocol` channel](https://discord.com/channels/1092455714431180995/1132296350894133379)

### Open-source agents and projects that have adopted Agent Protocol
- ✅ [Auto-GPT](https://github.com/Significant-Gravitas/Auto-GPT)
  - Track [PR here](https://github.com/Significant-Gravitas/Auto-GPT/pull/5044)
- 🚧 [Auto-GPT-Forge](https://github.com/Significant-Gravitas/Auto-GPT-Forge)
- 🚧 [Auto-GPT-Benchmarks](https://github.com/Significant-Gravitas/Auto-GPT-Benchmarks)
- 🚧 [babyagi](https://github.com/yoheinakajima/babyagi)
  - Track [PR here](https://github.com/yoheinakajima/babyagi/pull/356). Waiting for merge.
- 🚧 [smol developer](https://github.com/smol-ai/developer)
  - Track [PR here](https://github.com/smol-ai/developer/pull/123). Waiting for merge.
- 🚧 [beebot](https://github.com/AutoPackAI/beebot)
  - Might require GraphQL and more features. See [issue here](https://github.com/e2b-dev/agent-protocol/issues/9).

### Platforms supporting Agent Protocol
- [e2b](https://e2b.dev)

## How to use this protocol?
### Supported languages:
- Python
- 🚧 *JavaScript/TypeScript*

### Python

```sh
pip install agent-protocol
```
_You can find the full example [in the Python SDK directory](./agent/python/README.md)_

### 🚧 JavaScript/TypeScript 
```sh
npm i agent-protocol
```
