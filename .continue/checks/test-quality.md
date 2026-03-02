# Test Quality Check

Review the diff for violations of this project's test style guide:

1. **Test framework**: Use `pytest` — NOT `unittest`. Flag any `unittest.TestCase` subclasses or `self.assert*` calls.
2. **No trivial tests**: Every test must cover at least one meaningful point of failure, not just `assert True` or smoke tests.
3. **Inline assertions**: Do NOT split test logic like `result = func(); assert result == b`. Instead write `assert func() == b` directly.
4. **parametrize format**: The first argument to `pytest.mark.parametrize` must be a **tuple** (not a string, not a list). The second argument must be a **list** (not a tuple).
   - BAD: `@pytest.mark.parametrize("x,y", [...])`  — first arg is a string
   - BAD: `@pytest.mark.parametrize(["x", "y"], [...])` — first arg is a list
   - GOOD: `@pytest.mark.parametrize(("x", "y"), [...])`
5. **No unnecessary mocking/patching**: Do not mock/patch unless explicitly required.

For each violation, state: file path, line number, severity (Error/Warning), and how to fix it.
If there are no violations, state PASS.
If there are violations, state FAIL.
