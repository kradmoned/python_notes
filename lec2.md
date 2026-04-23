# List

- List concatenation `+`
- Contains `in`
is tuple mutable in python
# Tuples

- Tuples are collections of data that are ordered and unchangeable. You can think of a tuple as a List with a fixed size. Tuples are created with round brackets

```python
my_tuple = ("this is a tuple", 45, True)
print(my_tuple[0])
# this is a tuple
print(my_tuple[1])
# 45
print(my_tuple[2])
# True
```

- It is considered bad practice to store items of different types in list but same cant be said for tuples as they have same size
- It is used to store very small group

```python
dog = ("Fido", 4)
```

- Single item tuple
  `dog = (fido,)`

- Tuple Unpacking

```python
dog = ("Fido", 4)
dog_name, dog_age = dog
print(dog_name)
# Fido
print(dog_age)
# 4
```

- Value can also be gotten throug indexing ie dog[1]

- # Dictionaries
- ## Dictionariese Key -> value pairs

```python
# use curly braces
# add key-value pairs
car = {
  "brand": "Toyota",
  "model": "Camry",
  "year": 2019,
}
```

- ## You can't have two of the same keys in the same dictionary

- ## Accessing value from dictionary

```python
car = {
    "make": "Toyota",
    "model": "Camry"
}
print(car["make"])
# Prints: Toyota
```

- ## Setting dictionary values, you do not need to set values at the time of creation values can be set later using `=` operator

```python
planets = {}
planets["Earth"] = True
planets["Pluto"] = False
print(planets["Pluto"])
# Prints False
```

- ## Updating Dictionary values

- If you try to set the value again the dictionary will be updated

```python
planets = {
    "Pluto": True,
}
planets["Pluto"] = False
print(planets["Pluto"])
# Prints False
```

- # Deleting value from dictionary

- It can be done using `del` keyword , deleting a non existent key will return an error

# In key word

# Dictionary iteration

- Exercise merge two dictionaries and return a merged dictionary

```python
def merge(dic1, dic2):
```
