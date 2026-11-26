# Chapter 6 — Agent Identity, Roles and Responsibilities

<text>**Status:** In progress</text>

## Chapter scope

This chapter introduces the elements needed to distinguish and organise agents within a larger system:

1. **Agent identity:** what distinguishes one agent from another.
2. **Agent role:** the function it performs.
3. **Agent responsibilities:** what it is expected to accomplish.
4. **Agent authority:** which decisions and actions it is allowed to perform.
5. **Agent boundaries:** what it must not do.
6. **Agent relationships:** which other agents it can communicate or collaborate with.
7. **Agent accountability:** how actions and decisions can be traced and assessed.

## 6.1 Agent Identity

### Core question

How does a system recognise an individual agent and distinguish it from every other agent?

In a system containing many agents, each should have a distinguishable identity. This allows the system to establish which agent is performing a task, its assigned role, responsibilities, permissions, communication relationships and activity history.

### Identity is separate from the underlying model

An agent's identity is not the same as the AI model powering it.

- Multiple agents can use the same AI model while having different identities.
- Those agents can have different roles, configurations, permissions and memory.
- An agent's underlying model may change without necessarily changing its identity.

This separation allows agents to be managed as distinct system components even when they share a model.

### Principle established

**Every agent should have a clearly identifiable identity independent of the model powering it.**

### Illustrative example

A learning example uses separate identifiers for:
- A market data collection agent.
- An information verification agent.
- A market analysis agent.

The identifiers and names are illustrative. This chapter has not yet selected a technical identity standard or implementation mechanism.

## Remaining subsections

- **6.2 Agent Roles** — how an agent's identity translates into a defined function within a larger system.
- **6.3 Agent Responsibilities** — to be developed.
- **6.4 Agent Authority** — to be developed.
- **6.5 Agent Boundaries** — to be developed.
- **6.6 Agent Relationships** — to be developed.
- **6.7 Agent Accountability** — to be developed.

Continue with 6.2 Agent Roles. Do not treat the uncompleted subsection headings as lessons already covered.
