# Regular Expressions (Regex) Cheat Sheet

This cheat sheet contains common Python regex patterns that are useful for validation, extraction, and text cleaning.

## 1. Basic anchors

| Pattern | Meaning | Example |
|---|---|---|
| `^` | Start of string | `^hello` matches `hello` at the beginning |
| `$` | End of string | `world$` matches `world` at the end |
| `\A` | Start of string (more strict in some engines) | `\Ahello` |
| `\Z` | End of string (more strict in some engines) | `world\Z` |

## 2. Character classes

| Pattern | Meaning | Example |
|---|---|---|
| `[abc]` | Any one of a, b, c | `b` matches `b` |
| `[a-z]` | Any lowercase letter | `^[a-z]+$` |
| `[A-Z]` | Any uppercase letter | `^[A-Z]+$` |
| `[0-9]` | Any digit | `^[0-9]+$` |
| `\d` | Digit | `\d{2}` |
| `\D` | Non-digit | `\D+` |
| `\w` | Word character: letters, digits, underscore | `\w+` |
| `\W` | Non-word character | `\W+` |
| `\s` | Whitespace | `\s+` |
| `\S` | Non-whitespace | `\S+` |
| `.` | Any character except newline | `a.b` matches `acb` |

## 3. Quantifiers

| Pattern | Meaning | Example |
|---|---|---|
| `?` | Zero or one | `colou?r` matches `color` or `colour` |
| `*` | Zero or more | `a*` |
| `+` | One or more | `a+` |
| `{n}` | Exactly n times | `\d{4}` |
| `{n,}` | At least n times | `\d{2,}` |
| `{n,m}` | Between n and m times | `\d{2,4}` |

## 4. Groups and alternation

| Pattern | Meaning | Example |
|---|---|---|
| `(abc)` | Capturing group | `(hello)` |
| `(?:abc)` | Non-capturing group | `(?:Mr|Ms)` |
| `|` | Alternation (OR) | `cat|dog` |
| `(...)` | Grouping for logic | `(red|blue)` |

## 5. Escaping special characters

| Character | Escaped form |
|---|---|
| `.` | `\.` |
| `*` | `\*` |
| `?` | `\?` |
| `+` | `\+` |
| `[` | `\[` |
| `]` | `\]` |
| `(` | `\(` |
| `)` | `\)` |
| `{` | `\{` |
| `}` | `\}` |
| `|` | `\|` |
| `^` | `\^` |
| `$` | `\$` |

## 6. Common useful patterns

### Match a word
```python
r'^[A-Za-z]+$'
```
Matches only letters.

### Match a whole number
```python
r'^\d+$'
```
Matches only digits.

### Match a decimal number
```python
r'^\d+(\.\d+)?$'
```
Matches integers or decimals like `12` or `12.5`.

### Match an email address
```python
r'^[\w\.-]+@[\w\.-]+\.\w+$'
```
Matches patterns like `name@example.com`.

### Match a simple URL
```python
r'https?://\S+'
```
Matches `http://` or `https://` links.

### Match a valid password (letters + digits + at least 8 chars)
```python
r'^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$'
```
Useful for basic password validation.

### Match a date in YYYY-MM-DD format
```python
r'^\d{4}-\d{2}-\d{2}$'
```
Matches values such as `2026-10-28`.

### Match a phone number
```python
r'^\+?[0-9]{10,15}$'
```
Matches simple international phone numbers.

### Match a hashtag
```python
r'#\w+'
```
Matches `#Python`, `#DataScience`.

### Match a username or identifier
```python
r'^[a-zA-Z_][a-zA-Z0-9_]*$'
```
Useful for variable names or usernames.

## 7. Boundaries and lookarounds

| Pattern | Meaning |
|---|---|
| `\bword\b` | Word boundary |
| `\B` | Not a word boundary |
| `(?=...)` | Positive lookahead |
| `(?!...)` | Negative lookahead |
| `(?<=...)` | Positive lookbehind |
| `(?<!...)` | Negative lookbehind |

### Example: word boundary
```python
r'\bcat\b'
```
Matches `cat` as a standalone word.

### Example: lookahead
```python
r'\d+(?= USD)'
```
Matches a number before the word `USD`.

## 8. Regex in Python examples

```python
import re

pattern = r'^[A-Za-z]+$'
text = 'Python'

if re.fullmatch(pattern, text):
    print('Valid')
else:
    print('Invalid')
```

```python
import re

text = 'Email: anna@gmail.com and bob@yahoo.com'
matches = re.findall(r'[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}', text)
print(matches)
```

## 9. Common metacharacters summary

| Symbol | Meaning |
|---|---|
| `.` | Any character except newline |
| `^` | Start of string |
| `$` | End of string |
| `*` | Zero or more |
| `+` | One or more |
| `?` | Zero or one |
| `{}` | Exact repetition |
| `[]` | Character class |
| `()` | Group |
| `|` | OR |
| `\` | Escape character |

## 10. Quick reminder

- Use `re.search()` to find a pattern anywhere in a string.
- Use `re.match()` to check only the beginning of a string.
- Use `re.fullmatch()` to match the entire string.
- Use `re.findall()` to extract all matches.
- Use `re.sub()` to replace matched text.

## 11. Useful Python regex methods

```python
re.search(pattern, text)
re.match(pattern, text)
re.fullmatch(pattern, text)
re.findall(pattern, text)
re.sub(pattern, replacement, text)
```

## 12. Example replacements

```python
import re
text = 'Contact: john@example.com'
cleaned = re.sub(r'@.*', '@gmail.com', text)
print(cleaned)
```

This cheat sheet is a practical starting point for working with regex in Python and data-handling exercises.
