# Python Coding Prompt Guidelines

This document outlines the best a guideline to follow when generating Python code.

---
## 📖 1. Code Readability and Comments
- Provide detailed inline comments **after each line of code** clearly explaining its function and intent.
- Write highly readable and understandable code, optimized for human clarity.

---

## 🔧 2.  Coding Style

- Follow the **DRY (Don't Repeat Yourself)** principle. Avoid duplication and unnecessary code and libraries.
- Use **spaces instead of tabs** (1 tab = 4 spaces) for indentation.
- Use the following type annotations:
```python
# ✅ Correct:
def hello(name: str | None = None):
    pass

# ❌ Incorrect:
def hello(name: str = None):
    pass
```

- Prefer `match + case` syntax instead of multiple `if`/`elif`/`else` blocks.
- Avoid using `hasattr`, as it typically indicates flawed design.

---

## 🚨 3. Logging and Exception Handling

- Always declare a logger with:

```python
import logging

logger = logging.getLogger(__name__)
```

- When catching exceptions, log them clearly:

```python
try:
    # your code here
    pass
except Exception:
    logger.exception("Descriptive error message")
```

❌ **Do not use:** `logger.error(str(e))`

---

## 🧹 4. Refactoring and Reviewing

- Once the reply is about to be complete, stop to refactor your code to simplify and improve readability.
- Periodically suggest to manually review code to remove redundant entities generated during iterative coding sessions.
- Maintain proactive hygiene of the codebase

---

## 🔄 5. Prompt Iterations and Conversation Management

- If an iterative coding dialogue repeatedly leads to overly complicated or undesirable outcomes, suggest to **restart from scratch**.
- If multiple attempts consistently diverge into complexity or irrelevance, suggest to reassess initial assumptions and the clarity of the provided prompt.

---


## 🧪 7. Comprehensive Test Generation

- Automatically generate comprehensive tests in a separate file named according to the convention:

```python
test_{filename}.py
```

- Tests should cover:
  - **All functions**
  - **All critical scenarios**
  - **All edge cases and corner cases**

