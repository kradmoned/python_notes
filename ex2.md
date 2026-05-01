# Complete the `get_character_record` function. It takes a character's `name`, `server`, `level`, and `rank` as individual inputs, and returns a dictionary with the following string keys

- `"name"`
- `"server"`
- `"level"`
- `"rank"`
- `"id"`

Create and return a dictionary with the keys above.
Assign each of the four inputs to the matching key, i.e., `"name": name`.
Next, we can't have two characters named `bloodwarrior123` on the same server!

For the fifth key, `id`, create a unique value as follows:
Concatenate the `name` and the `server` inputs with a `#` in the middle. For example, given:

- `name = "bloodwarrior123"`
- `server = "server1"`

Then the `id` field would be set to `bloodwarrior123#server1`.

```python
def get_character_record(name, server, level, rank):

    pass
```

# The `summarize_station_sales` function is supposed to build a dictionary of total items sold per cafeteria station. Each record is a dictionary with

- `"station"`: the station name
- `"items_sold"`: how many items that station sold in that record

**Expected behavior:**
Loop through all records and return a new dictionary where:

- Each key is a station name.
- Each value is the total `items_sold` for that station.
- If the same station appears more than once, its total should increase.
- If the input is empty, return an empty dictionary.

**Example:**

```python
records = [
    {"station": "grill", "items_sold": 4},
    {"station": "salad", "items_sold": 2},
    {"station": "grill", "items_sold": 3},
]
print(summarize_station_sales(records))
# Expected: {"grill": 7, "salad": 2}
```

```python
def summarize_station_sales(records):
    # Initialize an empty dictionary to store the totals


    # Loop through the records to calculate the total items sold per station
    # Hint: Check if the station already exists in your dictionary before adding to it


    return {} # Replace this with your final dictionary

# --- Test ---
records = [
    {"station": "grill", "items_sold": 4},
    {"station": "salad", "items_sold": 2},
    {"station": "grill", "items_sold": 3},
]
print(summarize_station_sales(records))
# Expected: {'grill': 7, 'salad': 2}
```

---

# **Exercise: Quest Status**

Fantasy Quest stores each character's progress in a nested dictionary structure. Here's what it looks like:

```json
{
  "character_name": "Kaladin",
  "quests": {
    "bridge_run": {
      "status": "In Progress"
    },
    "talk_to_syl": {
      "status": "Completed"
    }
  }
}
```

The values can change of course, but the structure will always be the same. For example, another character's progress might look like this:

```json
{
  "character_name": "Shallan",
  "quests": {
    "bridge_run": {
      "status": "Completed"
    },
    "talk_to_syl": {
      "status": "In Progress"
    }
  }
}
```

**Expected behavior:**
Complete the `get_quest_status` function. It accepts a `progress` dictionary (structure defined above) and should return the value of the `"status"` field specifically for the `"bridge_run"` quest.

- You do not need to use any loops for this task.
- **Hint:** You can chain dictionary keys on the progress dictionary to access the nested quest information inside another dictionary: `outer_dictionary["outer_key"]["inner_key"]`

```python
def get_quest_status(progress):
    # Chain the correct dictionary keys to access the bridge_run status


    return "" # Replace this string with your chained dictionary keys

# --- Test ---
kaladin_progress = {
    "character_name": "Kaladin",
    "quests": {
        "bridge_run": {
            "status": "In Progress",
        },
        "talk_to_syl": {
            "status": "Completed",
        },
    },
}

print(get_quest_status(kaladin_progress))
# Expected Output: In Progress
```

---

# **Exercise: Merge Dictionaries**

Guilds can merge in Fantasy Quest. We need to be able to take two player dictionaries (representing guilds) and merge them into a single guild.

**Instructions:**
Complete the `merge` function. It accepts two dictionaries as input and returns a new merged dictionary that contains all the keys and values from the input dictionaries.

Use only loops for this practice task:

1. Create an empty dictionary to hold the new merged result.
2. Iterate over the key/value pairs of `dict1` and add them to the merged dictionary.
3. Iterate over the key/value pairs of `dict2` and add them to the merged dictionary.
4. Return the newly merged dictionary.

_Note: If a key exists in both dictionaries, the value from the second dictionary should overwrite the value from the first dictionary._

**Example:**

```python
two_towers = {"Frodo": 56, "Aragorn": 10}
rotk = {"Aragorn": 100, "Gandalf": 809}
merged_dict = merge(two_towers, rotk)
print(merged_dict)
# Output: {'Frodo': 56, 'Aragorn': 100, 'Gandalf': 809}
```

```python
def merge(dict1, dict2):


    pass

two_towers = {"Frodo": 56, "Aragorn": 10}
rotk = {"Aragorn": 100, "Gandalf": 809}
merged_dict = merge(two_towers, rotk)
print(merged_dict)
```

---

# **Exercise: Build Market Item Summary**

**Objective:**
Complete the `build_item_summary` function. You are given a list of sale records, where each record is a dictionary. Your job is to build a new summary dictionary from scratch.

Each input record will always have an `"item"` key. Some records may also have a `"quantity"` or `"price"` key.

**Return Value:**
Return a dictionary with exactly these 4 keys:

```json
{
    "record_counts": {...},
    "total_quantities": {...},
    "latest_prices": {...},
    "grand_total_quantity": ...
}
```

**What each part means:**

- `"record_counts"`: how many records appeared for each item
- `"total_quantities"`: the total quantity for each item
- `"latest_prices"`: the most recent price seen for each item
- `"grand_total_quantity"`: the total quantity across all items

**Rules & Step-by-Step Plan:**

1. Create the result dictionary with empty values (`{}` for the nested dictionaries and `0` for the grand total).
2. Loop through each record and get the `"item"` value.
3. If this item is new, add default starting entries for it in `"record_counts"` and `"total_quantities"`.
4. Increase the record count for that item.
5. Read the quantity; if it is missing, use `0`.
6. Add that quantity to both the item's total quantity and the overall `"grand_total_quantity"`.
7. If a `"price"` exists in the record, update `"latest_prices"` for that item.
8. If the input list is empty, return the summary shape with empty dictionaries and `0`.

**Examples:**

```python
records1 = [
    {"item": "tea", "quantity": 2, "price": 3},
    {"item": "cake", "quantity": 1, "price": 5},
    {"item": "tea", "quantity": 4, "price": 4},
]
# Expected: {'record_counts': {'tea': 2, 'cake': 1}, 'total_quantities': {'tea': 6, 'cake': 1}, 'latest_prices': {'tea': 4, 'cake': 5}, 'grand_total_quantity': 7}

records2 = [
    {"item": "apple", "price": 2},
    {"item": "apple", "quantity": 3},
    {"item": "banana", "quantity": 2, "price": 1},
]
# Expected: {'record_counts': {'apple': 2, 'banana': 1}, 'total_quantities': {'apple': 3, 'banana': 2}, 'latest_prices': {'apple': 2, 'banana': 1}, 'grand_total_quantity': 5}
```

```python
def build_item_summary(records):


    pass

# --- Test your code ---
records1 = [
    {"item": "tea", "quantity": 2, "price": 3},
    {"item": "cake", "quantity": 1, "price": 5},
    {"item": "tea", "quantity": 4, "price": 4},
]
print(build_item_summary(records1))

records2 = [
    {"item": "apple", "price": 2},
    {"item": "apple", "quantity": 3},
    {"item": "banana", "quantity": 2, "price": 1},
]
print(build_item_summary(records2))
```
