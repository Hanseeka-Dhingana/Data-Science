## Table of Content
- Basics of Python    
- Python Data Structures (Lists, Dictionaries Tuples, Sets) and difference table
- Python Numpy  

<br>  
  


## Basics of Python

### What is Python?

Python is a **high-level, interpreted, and general-purpose programming language** that is easy to read and write.

### 🔹 Why Python is popular?

* Simple English-like syntax
* Less code, more work
* Used in **Data Science, AI, Web, Automation**
* Huge library support



### Python Syntax Example

```python
print("Hello, Python!")
```

👉 No semicolons, no complex brackets → very readable.

---

### Variables in Python

A variable stores data.

```python
age = 21
name = "Ali"
marks = 85.5
```

Python **automatically detects data type**.

---

###  Basic Data Types

| Data Type | Example      |
| --------- | ------------ |
| int       | 10           |
| float     | 5.6          |
| str       | "Python"     |
| bool      | True / False |

```python
x = 10        # int
y = 3.14      # float
z = "Data"    # string
```

---

### Conditional Statements

```python
if age >= 18:
    print("Eligible")
else:
    print("Not eligible")
```

---

### Loops

#### for loop

```python
for i in range(5):
    print(i)
```

#### while loop

```python
i = 1
while i <= 5:
    print(i)
    i += 1
```

## Core Python Data Structures 
When working with data, you rarely deal with a single number. You deal with collections of data (e.g., 1,000 ages, 500 customer names). Python provides four main ways to store and organize these collections.

#### **A. Lists (The Versatile Workhorse)**

A list is an ordered, changeable (mutable) collection that allows duplicate values. It is the most common data structure you will use.

* **Best for:** Storing a sequence of items where the order matters and you might need to add or remove items later.
* **Syntax:** Defined using square brackets `[]`.

```python
# Example: A list of customer ages
customer_ages = [25, 34, 25, 40, 19]

# You can modify them (Mutable)
customer_ages.append(50)         # Adds 50 to the end
customer_ages[0] = 26            # Changes the first age from 25 to 26

print(customer_ages) 
# Output: [26, 34, 25, 40, 19, 50]

```

#### **B. Tuples (The Locked Safe)**

A tuple is ordered like a list, but it is **immutable**, meaning once you create it, you cannot change, add, or remove items.

* **Best for:** Storing data that should never be altered accidentally (e.g., geographic coordinates, fixed configurations).
* **Syntax:** Defined using parentheses `()`.

```python
# Example: GPS coordinates (Latitude, Longitude)
store_location = (40.7128, -74.0060)

# store_location[0] = 41.0000  <-- THIS WILL CAUSE AN ERROR! Tuples cannot be changed.

```

#### **C. Sets (The Duplicate Killer)**

A set is an unordered collection of **unique** items. You cannot access items by their position (index) because there is no fixed order.

* **Best for:** Quickly removing duplicates from a dataset or checking if a specific item exists (membership testing).
* **Syntax:** Defined using curly braces `{}`.

```python
# Example: Finding unique products purchased
products_viewed = {"Laptop", "Mouse", "Keyboard", "Mouse", "Laptop"}

print(products_viewed) 
# Output: {'Keyboard', 'Mouse', 'Laptop'} (Notice duplicates are gone and order is random)

```

#### **D. Dictionaries (The Lookup Table)**

A dictionary stores data in **Key-Value pairs**. Instead of finding an item by its numerical position (like in a list), you find a "value" by looking up its unique "key."

* **Best for:** Storing attributes related to a specific entity, similar to a row in a database or a JSON file.
* **Syntax:** Defined using curly braces `{}` with keys and values separated by a colon `:`.

```python
# Example: Storing a single customer's profile
customer_profile = {
    "name": "Alice",
    "age": 28,
    "subscribed": True
}

# Looking up a value using its key
print(customer_profile["age"])  
# Output: 28

```

---

### **2. Data Structures Comparison Table**

| Data Structure | Ordered? | Mutable (Changeable)? | Allows Duplicates? | Syntax Example |
| --- | --- | --- | --- | --- |
| **List** | Yes | Yes | Yes | `[1, 2, 3]` |
| **Tuple** | Yes | **No** (Immutable) | Yes | `(1, 2, 3)` |
| **Set** | No | Yes | **No** | `{1, 2, 3}` |
| **Dictionary** | Yes (in modern Python) | Yes | Keys: No, Values: Yes | `{'A': 1, 'B': 2}` |

---

## **3. Introduction to NumPy (Numerical Python)**
While standard Python lists are great, they are incredibly slow when doing heavy math on millions of rows of data. This is where **NumPy** comes in. It is a third-party library that provides a new data structure called the **NumPy Array** (`ndarray`).

### **Why use NumPy instead of Python Lists?**

1. **Speed (C-Level Operations):** NumPy is written in the C programming language under the hood. It stores data in contiguous blocks of memory, making it up to 50x faster than standard Python lists.
2. **Memory Efficiency:** NumPy arrays consume significantly less RAM than Python lists.
3. **Vectorization:** You can perform mathematical operations on entire arrays at once without writing `for` loops.

**Example: The Power of Vectorization**
Imagine you have a list of prices and you want to add a $2 tax to every single price.

**The slow way (using standard Python Lists):**

```python
prices_list = [10, 20, 30]
taxed_prices = []

for price in prices_list:
    taxed_prices.append(price + 2) # You have to loop through one by one

```

**The fast way (using NumPy):**

```python
import numpy as np

# Create a NumPy array
prices_array = np.array([10, 20, 30])

# Add 2 to the entire array instantly (Vectorization)
taxed_array = prices_array + 2 

print(taxed_array)
# Output: [12 22 32]

```

NumPy is the mathematical foundation for almost every other Data Science tool in Python. Once you have your data in a NumPy array, you can instantly calculate means, medians, standard deviations, or perform complex matrix multiplications.

