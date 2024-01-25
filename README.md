# Wumpus-World-Inference-with-Propositional-Logic

This Python Jupyter Notebook focuses on using Propositional Logic to infer knowledge as an agent moves through the Wumpus World environment. The environment is defined using symbols A (Agent), B (Breeze), G (Gold), P (Pit), S (Stench), and W (Wumpus), and the logical relations between these symbols are established.

## Section 1: Propositional Logic in Wumpus World

### i. Define Knowledgebase
- **Symbols:**
  - A: Agent
  - B: Breeze
  - G: Gold
  - P: Pit
  - S: Stench
  - W: Wumpus

- **Logical Relations:**
  - The logical relation between a Pit and the Breeze in its neighboring squares.
  - The logical relation between the Wumpus and the Stench in its neighboring squares.

**Knowledgebase Schematic Diagram:**
```
    S | B | B | P
    --+---+---+--
    W | B | S | P
    --+---+---+--
    B | A | P | G
    --+---+---+--
    B | S | B | A
```

### ii. First Move Inference
- **Inference:**
  - Since there is no breeze or stench in the starting square, it is safe for the agent to make the first move.

### iii. Update Knowledgebase After First Move (Assuming Move to (1,1))
- **Percepts Received:**
  - No Breeze, No Stench

- **Inferences:**
  - Since there is no breeze or stench, the neighboring squares are safe, and the agent can move freely.

### iv. Inference for Next Move (Assuming Agent Moved to (1,2))
- **Inference:**
  - Since there is a breeze in (1,1), and the neighboring square (1,2) does not have a pit, it is safe to move to (1,2).

## Section 2: First Order Logic Knowledgebase

### i. Create FolKB
- **FolKB:**
  - Statements:
    - `Old_Aberdeen` is an area in the city of Aberdeen.
    - `Seaton_Estate` is part of `Old_Aberdeen` and has council housing.
    - High numbers of poorly qualified people live in `Seaton_Estate`.
    - Areas with council housing have high unemployment.
    - Poorly qualified people are unemployable.
    - Areas with unemployable people have high unemployment.
    - `Old_Aberdeen` is economically deprived.
    - Economic deprivation causes high unemployment.
    - Areas with high crime rates are known for high unemployment.

### ii. Forward Chaining Algorithm
- **Inference Steps:**
  - Starting with the given information, the forward chaining algorithm deduces areas in Aberdeen with high unemployment.
