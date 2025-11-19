# Codex MCA - Modular Context Architecture

> **"The novel is not a stream of text. It is a database of narrative entities."**

## Introduction
Welcome to the **Modular Context Architecture (MCA)**. This is not just a folder structure; it is a rigorous **Narrative System Architecture** designed to solve the fundamental problem of Long-Context AI Generation: **Consistency**.

Traditional methods treat a novel as a single, linear text file. This fails because LLMs suffer from the "Lost in the Middle" phenomenon—they forget details buried in 50,000 words of prose. MCA treats the novel as a **software repository**, where every character, location, and plot point is a discrete, structured entity.

## The Philosophy
1.  **Separation of Concerns**: Just as software has Model-View-Controller, MCA has **World-Story-System**.
2.  **Structured Data over Unstructured Text**: Agents respect YAML frontmatter far more than prose. We embed the "truth" of the story in machine-readable metadata.
3.  **Retrieval Augmented Generation (RAG)**: We do not feed the agent the entire book. We feed it the *relevant* context for the specific scene it is writing.

## Directory Structure

### 1. `/system` (The Controller)
This directory defines **WHO** the agent is and **HOW** it writes. It is the immutable logic of the project.
*   `author_persona.md`: The specific voice (e.g., "Papa Hemingway").
*   `writing_style_guide.md`: The rules of syntax, grammar, and formatting.
*   `negative_constraints.md`: Hard rules on what is *forbidden* (e.g., "No sentimentality").

### 2. `/world` (The Model)
This is the **Source of Truth**. If it's not in `/world`, it doesn't exist.
*   `/characters`: Each file is a character.
    *   **YAML Frontmatter**: Tracks state (Age, Scars, Inventory).
    *   **Body**: Biography and Voice.
*   `/locations`: Sensory details for every setting.
*   `/lore`: Abstract concepts, history, and magic systems.

### 3. `/story` (The View)
The actual output—the manuscript.
*   `outline.md`: The high-level roadmap.
*   `/drafts`: The prose itself, organized by chapter/scene.

### 4. `/meta` (Project Management)
*   `master_plan.md`: High-level phases.
*   `todo_list.md`: The backlog.

## The Agentic Workflow

### Step 1: Context Loading
When assigning a task (e.g., "Write Chapter 2"), the agent must dynamically load the relevant context.
*   *Wrong*: Reading the whole previous chapter.
*   *Right*: Reading `outline.md`, `Santiago.md`, `The_Skiff.md`, and `The_Sea.md`.

### Step 2: Execution & Recursive Updates
This is the most critical part. As the agent writes, it acts as a **Continuity Guardian**.
*   **Scenario**: Santiago cuts his hand on the line.
*   **Action**: The agent must **IMMEDIATELY** open `world/characters/Santiago.md` and update the YAML frontmatter:
    ```yaml
    physical_traits:
      hands: "Deep-creased scars... fresh cut on right palm."
    ```
*   **Result**: In Chapter 10, the agent will "know" the hand is cut without needing to re-read Chapter 2.

### Step 3: Version Control
Because every file is Markdown, this entire system should be version-controlled with **Git**. This allows for "Time Travel"—rolling back a character's death or a plot twist with surgical precision.

---

**This is the optimal way to co-author with AI.** It demands discipline, but it rewards you with a narrative consistency that "chatting" with a bot can never achieve.
