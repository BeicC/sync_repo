# Code Conventions Check

Review the diff for violations of this project's Python style guide:

1. **Type annotations**: Use built-in `list`, `dict`, `tuple` etc. — NOT `List`, `Dict`, `Tuple` from `typing`. Flag any `from typing import List/Dict/Tuple` or uses of those types.
2. **Path handling**: Use `pathlib.Path` — NOT `os.path.join`, `os.path.exists`, etc.
3. **Variable initialization**: Do not assign a variable just to immediately pass it to a function. Pass the expression directly.
   - BAD: `result = func(); Class(result)`
   - GOOD: `Class(func())`
4. **Exception handling**: Do not catch exceptions unless explicitly required. Bare `except Exception` or catching exceptions with no meaningful handling is a violation.
5. **Dataclasses for config**: Configuration objects should use `@dataclass`.
6. **Jinja templates**: Use `jinja2` for string templates, not f-strings or `.format()` for multi-line messages.
7. **Conciseness**: Flag unnecessarily verbose code that can be reduced.

For each violation, state: file path, line number, severity (Error/Warning), and how to fix it.
If there are no violations, state PASS.
If there are violations, state FAIL.
