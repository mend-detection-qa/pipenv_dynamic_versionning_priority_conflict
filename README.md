# Pipenv Test Case 10: Priority Conflict Resolution

## What This Tests
Tests that the priority chain is correctly followed when multiple version sources are present with conflicting versions.

## Expected
3.11.0 found through PyenvVersionFile

## Files
- `.python-version` - Contains `3.11.0` (highest priority)
- `Pipfile` - Contains `python_version = "3.8"` in requires section
- `Pipfile.lock` - Contains `"python_version": "3.8"` in _meta.requires

## Expected Behavior
Your version detection tool should detect **Python 3.11.0** from `.python-version`.

## Priority
This test validates the complete priority chain. Even though multiple sources specify Python 3.8, the `.python-version` file (highest priority) wins with 3.11.0.

## Note
This is a critical test case that ensures the priority chain is correctly implemented. The highest priority source must always take precedence regardless of what lower-priority sources specify.
