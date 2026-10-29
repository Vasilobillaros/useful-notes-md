# JSON in Python Cheat Sheet

JSON (JavaScript Object Notation) is a lightweight data format used to store and exchange structured data. Python has a built-in module called `json` for reading and writing JSON files.

## 1. Import the JSON module

```python
import json
```

## 2. Basic JSON data types

JSON supports the following data types:

- object -> Python `dict`
- array -> Python `list`
- string -> Python `str`
- number -> Python `int` or `float`
- boolean -> Python `bool`
- null -> Python `None`

Example JSON:

```json
{
  "name": "Alice",
  "age": 25,
  "city": "Athens",
  "is_student": true,
  "skills": ["Python", "SQL"],
  "address": {
    "country": "Greece"
  }
}
```

Equivalent Python dictionary:

```python
person = {
    "name": "Alice",
    "age": 25,
    "city": "Athens",
    "is_student": True,
    "skills": ["Python", "SQL"],
    "address": {
        "country": "Greece"
    }
}
```

## 3. Read JSON from a file

```python
import json

with open("data.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data)
```

### What it does
- opens the file in read mode
- reads the JSON content
- converts it into a Python object (usually a dictionary or list)

## 4. Write JSON to a file

```python
import json

data = {"name": "Alice", "age": 25}

with open("data.json", "w", encoding="utf-8") as file:
    json.dump(data, file, ensure_ascii=False, indent=4)
```

### Common arguments
- `indent=4` -> makes the JSON easier to read
- `ensure_ascii=False` -> preserves non-English characters like `é`, `α`, `Ω`
- `sort_keys=True` -> sorts dictionary keys alphabetically

## 5. Convert Python object to JSON string

```python
import json

person = {"name": "Alice", "age": 25}
json_string = json.dumps(person)
print(json_string)
```

This returns a JSON-formatted string, not a file.

## 6. Convert JSON string to Python object

```python
import json

json_string = '{"name": "Alice", "age": 25}'
person = json.loads(json_string)
print(person)
```

## 7. Working with nested JSON

```python
import json

json_data = '''
{
  "student": {
    "name": "Maria",
    "grades": [90, 85, 95]
  }
}
'''

student_data = json.loads(json_data)
print(student_data["student"]["name"])      # Maria
print(student_data["student"]["grades"])    # [90, 85, 95]
```

## 8. Accessing data in JSON

```python
import json

with open("data.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data["name"])
print(data["skills"][0])
print(data["address"]["country"])
```

## 9. Updating JSON data

```python
import json

with open("data.json", "r", encoding="utf-8") as file:
    data = json.load(file)

data["age"] = 26
data["skills"].append("JavaScript")

with open("data.json", "w", encoding="utf-8") as file:
    json.dump(data, file, indent=4)
```

## 10. Loading JSON from a URL or API response

```python
import json
import requests

response = requests.get("https://example.com/data.json")
data = response.json()
print(data)
```

If the response is already JSON, `response.json()` is often simpler than `json.loads()`.

## 11. Handling invalid JSON

Sometimes the file is not valid JSON. Use `try` and `except`.

```python
import json

try:
    with open("broken.json", "r", encoding="utf-8") as file:
        data = json.load(file)
    print(data)
except json.JSONDecodeError:
    print("The file is not valid JSON.")
except FileNotFoundError:
    print("The file does not exist.")
```

## 12. Pretty-printing JSON

```python
import json

data = {"name": "Alice", "city": "Athens"}
print(json.dumps(data, indent=4, ensure_ascii=False))
```

Example output:

```json
{
    "name": "Alice",
    "city": "Athens"
}
```

## 13. Common JSON functions in Python

| Function | Purpose |
|---|---|
| `json.load(file)` | Reads JSON from a file |
| `json.dump(obj, file)` | Writes JSON to a file |
| `json.loads(string)` | Converts a JSON string to Python |
| `json.dumps(obj)` | Converts Python to JSON string |
| `json.JSONDecodeError` | Raised when JSON is invalid |

## 14. Typical JSON workflow

```python
import json

# 1. Read JSON from file
with open("students.json", "r", encoding="utf-8") as f:
    students = json.load(f)

# 2. Modify data
for student in students:
    student["grade"] = student.get("grade", 0) + 1

# 3. Save updated JSON
with open("students.json", "w", encoding="utf-8") as f:
    json.dump(students, f, ensure_ascii=False, indent=4)
```

## 15. JSON and Python examples related to data handling

### Example: read a list of records

```python
import json

with open("employees.json", "r", encoding="utf-8") as f:
    employees = json.load(f)

for person in employees:
    print(person["name"], person["department"])
```

### Example: filter records

```python
import json

with open("employees.json", "r", encoding="utf-8") as f:
    employees = json.load(f)

filtered = [person for person in employees if person["age"] >= 30]
print(filtered)
```

## 16. Quick rules to remember

- JSON files are text files.
- Use `json.load()` for reading.
- Use `json.dump()` for writing.
- Use `json.loads()` for strings.
- Use `json.dumps()` for converting Python objects to strings.
- Indentation and `ensure_ascii=False` make JSON easier to read and handle.

## 17. Minimal example

```python
import json

# Python dictionary
book = {
    "title": "Python Basics",
    "author": "Alice",
    "pages": 200
}

# Convert to JSON string
text = json.dumps(book, indent=2)
print(text)

# Save to file
with open("book.json", "w", encoding="utf-8") as f:
    json.dump(book, f, indent=2)

# Read from file
with open("book.json", "r", encoding="utf-8") as f:
    loaded = json.load(f)

print(loaded["title"])
```

This cheat sheet is useful for JSON files in Python projects, especially when working with datasets, APIs, and data-cleaning tasks.
