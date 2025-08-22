# Python Collection Data Types - Complete Reference Guide

## Table of Contents
1. [Introduction](#introduction)
2. [Sequences](#sequences)
   - [List (Mutable)](#list-mutable)
   - [Tuple (Immutable)](#tuple-immutable)
   - [Range (Immutable)](#range-immutable)
   - [String (Immutable)](#string-immutable)
   - [Bytes (Immutable)](#bytes-immutable)
   - [Bytearray (Mutable)](#bytearray-mutable)
3. [Sets](#sets)
   - [Set (Mutable)](#set-mutable)
   - [Frozenset (Immutable)](#frozenset-immutable)
4. [Mapping](#mapping)
   - [Dictionary (Mutable)](#dictionary-mutable)
5. [Memory and Performance Considerations](#memory-and-performance-considerations)
6. [Best Practices](#best-practices)
7. [Quick Reference Summary](#quick-reference-summary)

---

## Introduction

Python collection data types are fundamental structures for organizing and manipulating data. They are classified into three main categories based on their characteristics and behavior:

1. **Sequences**: Ordered collections with indexed access
2. **Sets**: Unordered collections of unique elements
3. **Mapping**: Key-value pair collections

Understanding the mutability, performance characteristics, and appropriate use cases for each collection type is crucial for writing efficient Python code.

---

## Sequences

Sequences are ordered collections that support indexing, slicing, and iteration. They maintain the insertion order of elements.

### List (Mutable)

**Definition**: An ordered, mutable collection that can contain duplicate elements of any data type.

#### Key Characteristics:
- **Mutability**: Fully mutable (can add, remove, modify elements)
- **Ordering**: Maintains insertion order
- **Duplicates**: Allows duplicate elements
- **Indexing**: Supports positive and negative indexing
- **Memory**: Dynamic array implementation with over-allocation for efficiency

#### Common Methods:
```python
# Creation
my_list = [1, 2, 3, 4, 5]
empty_list = []
list_from_iterable = list("hello")  # ['h', 'e', 'l', 'l', 'o']

# Adding elements
my_list.append(6)           # Add single element at end
my_list.extend([7, 8])      # Add multiple elements at end
my_list.insert(0, 0)        # Insert at specific position

# Removing elements
my_list.remove(3)           # Remove first occurrence of value
popped = my_list.pop()      # Remove and return last element
popped_at = my_list.pop(0)  # Remove and return element at index
del my_list[1]              # Delete element at index
my_list.clear()             # Remove all elements

# Searching and counting
index = my_list.index(5)    # Find index of first occurrence
count = my_list.count(2)    # Count occurrences

# Sorting and reversing
my_list.sort()              # Sort in place (ascending)
my_list.sort(reverse=True)  # Sort in place (descending)
my_list.reverse()           # Reverse in place

# Copying
shallow_copy = my_list.copy()
deep_copy = my_list[:]      # Slice copy
```

#### Performance Characteristics:
- Access by index: O(1)
- Append: O(1) amortized
- Insert at beginning: O(n)
- Search: O(n)
- Delete: O(n) for arbitrary position

#### Use Cases:
- When you need a mutable, ordered collection
- Implementing stacks (using append/pop)
- Building dynamic arrays
- Storing data that changes frequently

### Tuple (Immutable)

**Definition**: An ordered, immutable collection that can contain duplicate elements of any data type.

#### Key Characteristics:
- **Mutability**: Immutable (cannot modify after creation)
- **Ordering**: Maintains insertion order
- **Duplicates**: Allows duplicate elements
- **Indexing**: Supports positive and negative indexing
- **Memory**: More memory-efficient than lists
- **Hashable**: Can be used as dictionary keys or set elements

#### Common Operations:
```python
# Creation
my_tuple = (1, 2, 3, 4, 5)
single_element = (1,)       # Note the comma for single element
empty_tuple = ()
tuple_from_iterable = tuple("hello")  # ('h', 'e', 'l', 'l', 'o')

# Accessing elements
first = my_tuple[0]         # First element
last = my_tuple[-1]         # Last element
slice_tuple = my_tuple[1:4] # Slicing

# Methods
index = my_tuple.index(3)   # Find index of first occurrence
count = my_tuple.count(2)   # Count occurrences

# Unpacking
a, b, c, d, e = my_tuple    # Unpack all elements
first, *middle, last = my_tuple  # Extended unpacking

# Named tuples (from collections module)
from collections import namedtuple
Point = namedtuple('Point', ['x', 'y'])
p = Point(10, 20)
print(p.x, p.y)            # Accessing by name
```

#### Performance Characteristics:
- Access by index: O(1)
- Search: O(n)
- Creation: Faster than lists
- Memory usage: Lower than lists

#### Use Cases:
- Representing immutable data (coordinates, database records)
- Function return values (multiple values)
- Dictionary keys (when hashable)
- Configuration data that shouldn't change

### Range (Immutable)

**Definition**: An immutable sequence of numbers, commonly used for looping.

#### Key Characteristics:
- **Mutability**: Immutable
- **Memory**: Memory-efficient (stores only start, stop, step)
- **Lazy**: Generates values on demand
- **Arithmetic progression**: Represents arithmetic sequences

#### Common Usage:
```python
# Creation
range_obj = range(10)           # 0 to 9
range_with_start = range(2, 10) # 2 to 9
range_with_step = range(0, 10, 2)  # 0, 2, 4, 6, 8

# Converting to list for display
print(list(range(5)))           # [0, 1, 2, 3, 4]
print(list(range(1, 6)))        # [1, 2, 3, 4, 5]
print(list(range(10, 0, -1)))   # [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]

# Common operations
len_range = len(range(10))      # Length
contains = 5 in range(10)       # Membership test
index_val = list(range(10))[5]  # Index access (inefficient)

# Iteration (most common use)
for i in range(5):
    print(i)

# More efficient for checking membership and indexing
r = range(0, 100, 5)
print(25 in r)                  # True (efficient)
```

#### Performance Characteristics:
- Memory: O(1) regardless of range size
- Access: O(1) for membership testing and length
- Iteration: O(n) but memory-efficient

#### Use Cases:
- Loop iteration
- Generating sequences of numbers
- Indexing operations
- Memory-efficient number sequences

### String (Immutable)

**Definition**: An immutable sequence of Unicode characters.

#### Key Characteristics:
- **Mutability**: Immutable
- **Encoding**: Unicode (UTF-8)
- **Indexing**: Supports positive and negative indexing
- **Rich methods**: Extensive string manipulation methods

#### Common Methods:
```python
# Creation
my_string = "Hello, World!"
empty_string = ""
multiline = """This is a
multiline string"""

# Case methods
upper_str = my_string.upper()       # "HELLO, WORLD!"
lower_str = my_string.lower()       # "hello, world!"
title_str = my_string.title()       # "Hello, World!"
swapped = my_string.swapcase()      # "hELLO, wORLD!"

# Searching methods
index = my_string.find("World")     # Returns index or -1
starts = my_string.startswith("Hello")  # True
ends = my_string.endswith("!")      # True
count = my_string.count("l")        # Count occurrences

# Modification methods (return new strings)
replaced = my_string.replace("World", "Python")  # "Hello, Python!"
stripped = "  hello  ".strip()     # "hello"
split_str = "a,b,c".split(",")      # ["a", "b", "c"]
joined = ",".join(["a", "b", "c"])  # "a,b,c"

# Formatting
name = "Alice"
age = 30
formatted = f"Name: {name}, Age: {age}"  # f-string
formatted2 = "Name: {}, Age: {}".format(name, age)  # .format()
formatted3 = "Name: %s, Age: %d" % (name, age)  # % formatting

# String validation
is_alpha = "abc".isalpha()          # True
is_digit = "123".isdigit()          # True
is_alnum = "abc123".isalnum()       # True
```

#### Performance Characteristics:
- Access by index: O(1)
- Search: O(n)
- Concatenation: O(n) - creates new string
- Slicing: O(k) where k is slice length

#### Use Cases:
- Text processing and manipulation
- User input handling
- File paths and names
- Template strings

### Bytes (Immutable)

**Definition**: An immutable sequence of integers in the range 0-255, representing byte values.

#### Key Characteristics:
- **Mutability**: Immutable
- **Element type**: Integers (0-255)
- **Encoding**: Works with various encodings
- **Binary data**: Ideal for binary data handling

#### Common Operations:
```python
# Creation
byte_literal = b"Hello"             # Bytes literal
from_string = "Hello".encode('utf-8')  # String to bytes
from_list = bytes([72, 101, 108, 108, 111])  # From list
empty_bytes = b""

# String-like methods
upper_bytes = byte_literal.upper()  # b"HELLO"
find_result = byte_literal.find(b"ll")  # 2
split_bytes = b"a,b,c".split(b",")  # [b'a', b'b', b'c']

# Conversion
to_string = byte_literal.decode('utf-8')  # "Hello"
hex_repr = byte_literal.hex()       # "48656c6c6f"
from_hex = bytes.fromhex("48656c6c6f")  # b'Hello'

# File operations
with open('file.txt', 'rb') as f:
    content = f.read()              # Returns bytes

# Network operations example
import socket
data = b"GET / HTTP/1.1\r\n\r\n"
# socket.send(data)
```

#### Performance Characteristics:
- Similar to strings for most operations
- More efficient for binary data than strings
- Conversion to/from strings has encoding overhead

#### Use Cases:
- File I/O operations (binary mode)
- Network programming
- Cryptographic operations
- Image/audio processing

### Bytearray (Mutable)

**Definition**: A mutable sequence of integers in the range 0-255, representing byte values.

#### Key Characteristics:
- **Mutability**: Fully mutable
- **Element type**: Integers (0-255)
- **Dynamic**: Can grow and shrink
- **Efficiency**: More efficient than creating new bytes objects

#### Common Operations:
```python
# Creation
byte_array = bytearray(b"Hello")
from_string = bytearray("Hello", 'utf-8')
from_size = bytearray(10)           # 10 zero bytes
empty_ba = bytearray()

# Modification operations
byte_array.append(33)               # Add byte (33 is '!')
byte_array.extend(b" World")        # Extend with bytes
byte_array.insert(0, 72)            # Insert at position
byte_array.remove(108)              # Remove first occurrence of value
del byte_array[0]                   # Delete by index

# String-like methods (return new bytearray)
upper_ba = byte_array.upper()
replaced = byte_array.replace(b"Hello", b"Hi")

# In-place operations
byte_array.reverse()                # Reverse in place
byte_array.clear()                  # Remove all elements

# Conversion
to_bytes = bytes(byte_array)        # Convert to immutable bytes
to_string = byte_array.decode('utf-8')  # Convert to string
```

#### Performance Characteristics:
- Access/modification: O(1)
- Append: O(1) amortized
- Insert/delete: O(n)
- More efficient than bytes for frequent modifications

#### Use Cases:
- Buffer operations
- Stream processing
- Binary data manipulation
- Network protocols implementation

---

## Sets

Sets are unordered collections of unique elements, primarily used for membership testing and eliminating duplicates.

### Set (Mutable)

**Definition**: A mutable, unordered collection of unique, hashable elements.

#### Key Characteristics:
- **Mutability**: Mutable (can add/remove elements)
- **Uniqueness**: No duplicate elements
- **Hashable elements**: Elements must be hashable
- **Unordered**: No guaranteed order (though CPython 3.7+ maintains insertion order)
- **Mathematical operations**: Supports set theory operations

#### Common Operations:
```python
# Creation
my_set = {1, 2, 3, 4, 5}
empty_set = set()                   # Note: {} creates empty dict
from_list = set([1, 2, 2, 3, 3])   # {1, 2, 3} - duplicates removed
from_string = set("hello")          # {'h', 'e', 'l', 'o'}

# Adding elements
my_set.add(6)                       # Add single element
my_set.update([7, 8, 9])            # Add multiple elements
my_set.update({10, 11}, [12, 13])   # Multiple iterables

# Removing elements
my_set.remove(5)                    # Raises KeyError if not found
my_set.discard(100)                 # No error if not found
popped = my_set.pop()               # Remove and return arbitrary element
my_set.clear()                      # Remove all elements

# Set operations
set1 = {1, 2, 3, 4}
set2 = {3, 4, 5, 6}

union = set1 | set2                 # {1, 2, 3, 4, 5, 6}
intersection = set1 & set2          # {3, 4}
difference = set1 - set2            # {1, 2}
sym_diff = set1 ^ set2              # {1, 2, 5, 6}

# Method versions
union_method = set1.union(set2)
intersection_method = set1.intersection(set2)
difference_method = set1.difference(set2)
sym_diff_method = set1.symmetric_difference(set2)

# Set relationships
is_subset = {1, 2}.issubset({1, 2, 3, 4})      # True
is_superset = {1, 2, 3}.issuperset({1, 2})     # True
is_disjoint = {1, 2}.isdisjoint({3, 4})        # True

# Membership testing
contains = 3 in my_set              # Very fast O(1) average
```

#### Performance Characteristics:
- Membership testing: O(1) average, O(n) worst case
- Add/remove: O(1) average
- Set operations: O(min(len(s1), len(s2))) for intersection

#### Use Cases:
- Removing duplicates from sequences
- Fast membership testing
- Mathematical set operations
- Finding unique elements

### Frozenset (Immutable)

**Definition**: An immutable version of set that can be used as dictionary keys or set elements.

#### Key Characteristics:
- **Mutability**: Immutable
- **Hashable**: Can be used as dict keys or set elements
- **All set operations**: Supports same operations as set (except modification)

#### Common Operations:
```python
# Creation
frozen = frozenset([1, 2, 3, 4])
empty_frozen = frozenset()
from_set = frozenset({1, 2, 3})

# All query operations work the same
contains = 2 in frozen              # True
length = len(frozen)                # 4

# Set operations return new frozensets
fs1 = frozenset([1, 2, 3])
fs2 = frozenset([3, 4, 5])
union = fs1 | fs2                   # frozenset({1, 2, 3, 4, 5})

# Can be used as dictionary keys
dict_with_frozenset_keys = {
    frozenset([1, 2]): "value1",
    frozenset([3, 4]): "value2"
}

# Can be elements of sets
set_of_frozensets = {
    frozenset([1, 2]),
    frozenset([3, 4])
}
```

#### Performance Characteristics:
- Same as set for read operations
- Cannot be modified, so no modification performance

#### Use Cases:
- Dictionary keys when you need set-like keys
- Set elements when you need sets of sets
- Immutable set representation
- Configuration data

---

## Mapping

### Dictionary (Mutable)

**Definition**: A mutable collection of key-value pairs with unique keys.

#### Key Characteristics:
- **Mutability**: Fully mutable
- **Key uniqueness**: Keys must be unique and hashable
- **Ordered**: Maintains insertion order (Python 3.7+)
- **Dynamic**: Can grow and shrink
- **Fast lookup**: Average O(1) access time

#### Common Operations:
```python
# Creation
my_dict = {"a": 1, "b": 2, "c": 3}
empty_dict = {}
dict_from_pairs = dict([("x", 1), ("y", 2)])
dict_comprehension = {x: x**2 for x in range(5)}

# Accessing elements
value = my_dict["a"]                # Returns 1, KeyError if not found
safe_value = my_dict.get("d", 0)    # Returns 0 if key not found
safe_value2 = my_dict.get("d")      # Returns None if key not found

# Adding/modifying elements
my_dict["d"] = 4                    # Add new key-value pair
my_dict.update({"e": 5, "f": 6})    # Update with multiple pairs
my_dict.update(g=7, h=8)            # Update with keyword arguments

# Removing elements
del my_dict["a"]                    # Delete key, KeyError if not found
popped = my_dict.pop("b")           # Remove and return value
popped_default = my_dict.pop("z", "default")  # Return default if not found
key, value = my_dict.popitem()      # Remove and return arbitrary pair
my_dict.clear()                     # Remove all elements

# Dictionary methods
keys = my_dict.keys()               # Dict view of keys
values = my_dict.values()           # Dict view of values  
items = my_dict.items()             # Dict view of key-value pairs

# Dictionary views are dynamic
original = {"a": 1, "b": 2}
keys_view = original.keys()
print(list(keys_view))              # ['a', 'b']
original["c"] = 3
print(list(keys_view))              # ['a', 'b', 'c'] - view updated!

# Copying
shallow_copy = my_dict.copy()
dict_copy = dict(my_dict)

# Merging dictionaries (Python 3.9+)
dict1 = {"a": 1, "b": 2}
dict2 = {"c": 3, "d": 4}
merged = dict1 | dict2              # Union operator
dict1 |= dict2                      # In-place union

# Default dictionaries
from collections import defaultdict
dd = defaultdict(list)              # Default value is empty list
dd["key"].append("value")           # No KeyError, creates list automatically

# Ordered dictionary (before Python 3.7)
from collections import OrderedDict
ordered = OrderedDict([("a", 1), ("b", 2)])

# Counter (specialized dictionary)
from collections import Counter
counter = Counter("hello world")    # Counter({'l': 3, 'o': 2, ...})
```

#### Dictionary Comprehensions:
```python
# Basic comprehension
squares = {x: x**2 for x in range(5)}          # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}

# With condition
even_squares = {x: x**2 for x in range(10) if x % 2 == 0}

# From two lists
keys = ["a", "b", "c"]
values = [1, 2, 3]
combined = {k: v for k, v in zip(keys, values)}

# Nested comprehension
matrix = [[1, 2, 3], [4, 5, 6]]
flattened = {f"{i}_{j}": val for i, row in enumerate(matrix) for j, val in enumerate(row)}
```

#### Performance Characteristics:
- Access/insertion/deletion: O(1) average, O(n) worst case
- Memory overhead: Higher than lists/tuples due to hash table
- Iteration over keys/values/items: O(n)

#### Use Cases:
- Mapping relationships (ID to name, etc.)
- Caching/memoization
- Configuration settings
- Counting occurrences
- Lookup tables

---

## Memory and Performance Considerations

### Memory Usage Comparison:
```python
import sys

# Size comparison for 1000 elements
data = list(range(1000))

list_size = sys.getsizeof(data)                    # ~9KB
tuple_size = sys.getsizeof(tuple(data))            # ~8KB  
set_size = sys.getsizeof(set(data))                # ~32KB
dict_size = sys.getsizeof({x: x for x in data})   # ~36KB

print(f"List: {list_size} bytes")
print(f"Tuple: {tuple_size} bytes")  
print(f"Set: {set_size} bytes")
print(f"Dict: {dict_size} bytes")
```

### Performance Guidelines:

#### When to Use Lists:
- Need ordered, mutable collection
- Frequent appending/extending
- Index-based access required
- Small to medium datasets

#### When to Use Tuples:
- Immutable data representation
- Memory efficiency important
- Dictionary keys needed
- Function return multiple values

#### When to Use Sets:
- Need unique elements only
- Fast membership testing required
- Set operations (union, intersection, etc.)
- Duplicate removal

#### When to Use Dictionaries:
- Key-value relationships
- Fast lookups by key
- Counting/frequency analysis
- Configuration data

### Mutability Impact:
- **Mutable objects**: Cannot be dictionary keys or set elements
- **Immutable objects**: Can be hashed and used as keys
- **Memory**: Immutable objects often use less memory
- **Thread safety**: Immutable objects are inherently thread-safe

---

## Best Practices

### 1. Choose the Right Collection Type:
```python
# Use list for ordered, mutable data
tasks = ["task1", "task2", "task3"]

# Use tuple for immutable, structured data  
point = (10, 20)
rgb_color = (255, 128, 0)

# Use set for unique elements and fast lookups
unique_ids = {101, 102, 103, 104}

# Use dict for key-value mappings
user_data = {"name": "Alice", "age": 30, "email": "alice@example.com"}
```

### 2. Memory Efficiency:
```python
# Use tuple instead of list for immutable data
coordinates = (x, y)  # Better than [x, y] if not changing

# Use set for membership testing instead of list
valid_codes = {"A001", "B002", "C003"}  # Better than ["A001", "B002", "C003"]
if code in valid_codes:  # O(1) instead of O(n)
    process_code(code)
```

### 3. Performance Optimization:
```python
# List comprehension vs. loop
# Faster
squared = [x**2 for x in range(100)]

# Slower  
squared = []
for x in range(100):
    squared.append(x**2)

# Set operations vs. loops
set1 = {1, 2, 3, 4, 5}
set2 = {4, 5, 6, 7, 8}

# Faster
common = set1 & set2

# Slower
common = []
for item in set1:
    if item in set2:
        common.append(item)
```

### 4. Safe Operations:
```python
# Use .get() for dictionary access
value = my_dict.get("key", default_value)  # Safe
# value = my_dict["key"]  # May raise KeyError

# Use .discard() instead of .remove() for sets
my_set.discard("item")  # Safe, no error if not found
# my_set.remove("item")  # May raise KeyError

# Check before accessing
if "key" in my_dict:
    process(my_dict["key"])
```

---

## Quick Reference Summary

| Collection | Mutable | Ordered | Duplicates | Hashable Elements | Use Case |
|------------|---------|---------|------------|-------------------|----------|
| **List** | ✅ | ✅ | ✅ | No requirement | General purpose, dynamic arrays |
| **Tuple** | ❌ | ✅ | ✅ | No requirement | Immutable sequences, dict keys |
| **Range** | ❌ | ✅ | ❌ | N/A | Number sequences, loops |
| **String** | ❌ | ✅ | ✅ | N/A | Text processing |
| **Bytes** | ❌ | ✅ | ✅ | N/A | Binary data |
| **Bytearray** | ✅ | ✅ | ✅ | N/A | Mutable binary data |
| **Set** | ✅ | ❌* | ❌ | ✅ Required | Unique elements, fast lookup |
| **Frozenset** | ❌ | ❌* | ❌ | ✅ Required | Immutable sets, dict keys |
| **Dictionary** | ✅ | ✅** | N/A | ✅ Keys only | Key-value mapping |

*Insertion order maintained in CPython 3.7+ but not guaranteed by language specification  
**Guaranteed insertion order preservation since Python 3.7

### Time Complexity Quick Reference:

| Operation | List | Tuple | Set | Dict |
|-----------|------|-------|-----|------|
| Access by key/index | O(1) | O(1) | N/A | O(1) |
| Search | O(n) | O(n) | O(1) | O(1) |
| Insert | O(1)* / O(n) | N/A | O(1) | O(1) |
| Delete | O(n) | N/A | O(1) | O(1) |

*O(1) for append, O(n) for arbitrary position

---

This reference guide provides a comprehensive overview of Python's collection data types. Keep it handy for quick lookups when choosing the right data structure for your specific use case!