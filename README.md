# Simple LangGraph Workflow

This notebook demonstrates a minimal yet functional workflow using [LangGraph](https://github.com/langchain-ai/langgraph), a Python library for building stateful, graph-based AI systems. The primary objective is to illustrate how to define state, implement graph nodes, and execute a basic state transformation pipeline.

## Overview

The notebook includes:

- A definition of structured state using `TypedDict`.
- A graph built with `StateGraph`, representing sequential node execution.
- Simple node functions that modify the shared state.
- Execution of the compiled graph using a test input.

This example is suitable for engineers or researchers looking to get started with LangGraph for building AI agents or structured workflows.

## Contents

- `State` definition for type-safe state management.
- Graph construction using `add_node` and `set_entry_point`.
- Node logic for step-wise state updates.
- Graph compilation and invocation with example input.

## Technologies

- Python 3.10+
- `langgraph`
- `typing_extensions.TypedDict`

## Example Usage

```python
class State(TypedDict):
    graph_info: str

def bedminton_node(state: State) -> State:
    return {"graph_info": state["graph_info"] + " Bedminton"}
