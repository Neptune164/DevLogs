# DevLog

## Date
2026-03-21

## Workload

## Problem Shooting

- 1.  

### Learning
#### 1. Python Type Intro
- Type hints, use colons(:), not equals(=).
```python
def get_full_name(first_name:str, last_name:str):
    full_name = first_name.title() + " " + last_name.title()
	return full_name
```

- `typing` module
- Declare something has "any type":
```python
from typing import Any
def some_func(data: Any):
    print(data)
```

- **Generic types**: list, tuple, set and dict.
```python
def process_items(items: list[str]):
    for ite in items:
        print(item)
```
- **Union**: several types, using vertical bar(|)
- Like C++, a type can also be a class
- **Pydantic Models**: Python library, perform data validation.

#### 2. Shortcuts in the visual mode of Vim
- **0**: Jump to the first character of a row
- **$**: Jump to the last character of a row

#### 3. Concurrency and async/await in FastAPI
- **TL;DR**: Too Long; Didn't Read
- If you're using hird party libraries that tell you to use `await`. Then, declare your path operation functions with `async def`, like:
```python
@app.get('/')
async def read_results():
    results = await some_library()
    return reults
```
- Burger orders and crush example

