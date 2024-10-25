Here are the exercises from before, with Python code answers for each:

---

### 1. Basic Data Types

1. **Print Integer and Float**  
   ```python
   # Solution
   int_var = 10
   float_var = 5.5
   print(int_var, float_var)
   ```

2. **Type Checking**  
   ```python
   # Solution
   print(type(int_var))  # Output: <class 'int'>
   print(type(float_var))  # Output: <class 'float'>
   ```

3. **Convert Data Types**  
   ```python
   # Solution
   float_to_int = int(float_var)
   int_to_float = float(int_var)
   print("Float to Int:", float_to_int)  # Output: 5
   print("Int to Float:", int_to_float)  # Output: 10.0
   ```

---

### 2. String Manipulation

1. **Basic String Operations**  
   ```python
   # Solution
   text = "Hello, Python!"
   print(len(text))  # Output: 13
   print(text.upper())  # Output: "HELLO, PYTHON!"
   ```

2. **String Slicing**  
   ```python
   # Solution
   print(text[7:13])  # Output: "Python"
   ```

3. **Concatenate Strings**  
   ```python
   # Solution
   greeting = "Hello"
   language = "Python"
   result = greeting + ", " + language + "!"
   print(result)  # Output: "Hello, Python!"
   ```

---

### 3. Boolean Logic

1. **Boolean Evaluation**  
   ```python
   # Solution
   is_raining = True
   is_sunny = False
   print(is_raining and is_sunny)  # Output: False (both are not True)
   ```

2. **Boolean Conversion**  
   ```python
   # Solution
   print(bool(10))  # Output: True
   print(bool(0))   # Output: False
   ```

---

### 4. Collections: Lists, Tuples, Sets, and Dictionaries

1. **List Operations**  
   ```python
   # Solution
   numbers = [1, 2, 3, 4, 5]
   numbers.append(6)
   numbers.pop(2)  # Removes the third item (index 2)
   print(numbers)  # Output: [1, 2, 4, 5, 6]
   ```

2. **Tuple Creation**  
   ```python
   # Solution
   colors = ("red", "green", "blue")
   print(colors)  # Output: ("red", "green", "blue")
   # Attempting to change a tuple will raise an error, e.g., colors[0] = "yellow"
   ```

3. **Set Operations**  
   ```python
   # Solution
   my_set = {1, 2, 3}
   my_set.add(4)
   my_set.add(2)  # Duplicate values are ignored in sets
   print(my_set)  # Output: {1, 2, 3, 4}
   ```

4. **Dictionary Operations**  
   ```python
   # Solution
   person = {"name": "Alice", "age": 25, "city": "New York"}
   print(person["name"])  # Output: Alice
   person["country"] = "USA"
   print(person)  # Output: {"name": "Alice", "age": 25, "city": "New York", "country": "USA"}
   ```

---

### 5. Advanced Exercises

1. **Type Conversion**  
   ```python
   # Solution
   user_input = int(input("Enter an integer: "))
   print("As Integer:", user_input)  # Example output: 5
   print("As Float:", float(user_input))  # Example output: 5.0
   print("As String:", str(user_input))  # Example output: "5"
   ```

2. **List and Dictionary Combination**  
   ```python
   # Solution
   students = [
       {"name": "Alice", "score": 85},
       {"name": "Bob", "score": 92},
       {"name": "Charlie", "score": 78}
   ]
   
   for student in students:
       print(f"{student['name']} scored {student['score']}")
   # Output:
   # Alice scored 85
   # Bob scored 92
   # Charlie scored 78
   ```

3. **Nested Dictionary**  
   ```python
   # Solution
   library = {
       "fiction": ["1984", "Brave New World", "Fahrenheit 451"],
       "non-fiction": ["Sapiens", "Educated", "The Wright Brothers"]
   }
   
   for genre, books in library.items():
       print(f"{genre.capitalize()} books: {', '.join(books)}")
   # Output:
   # Fiction books: 1984, Brave New World, Fahrenheit 451
   # Non-fiction books: Sapiens, Educated, The Wright Brothers
   ```

4. **User Input Practice**  
   ```python
   # Solution
   user_info = {}
   user_info["name"] = input("Enter your name: ")
   user_info["age"] = input("Enter your age: ")
   user_info["favorite_color"] = input("Enter your favorite color: ")
   print(user_info)
   # Output example: {'name': 'Alice', 'age': '25', 'favorite_color': 'blue'}
   ```

---

### 6. Challenges

1. **Data Summarizer**  
   ```python
   # Solution
   user_input = input("Enter a list of integers separated by commas: ")
   numbers = list(map(int, user_input.split(',')))
   
   total = sum(numbers)
   average = total / len(numbers)
   largest = max(numbers)
   smallest = min(numbers)
   
   print("Sum:", total)
   print("Average:", average)
   print("Largest:", largest)
   print("Smallest:", smallest)
   ```

2. **Shopping Cart System**  
   ```python
   # Solution
   cart = []
   
   while True:
       item = input("Enter item name (or 'done' to finish): ")
       if item.lower() == 'done':
           break
       price = float(input(f"Enter price for {item}: "))
       quantity = int(input(f"Enter quantity for {item}: "))
       
       cart.append({"item": item, "price": price, "quantity": quantity})
   
   print("\nShopping Cart Summary:")
   total_cost = 0
   for product in cart:
       item_total = product["price"] * product["quantity"]
       total_cost += item_total
       print(f"{product['item']} - {product['quantity']} @ {product['price']} each = {item_total}")
   
   print("\nTotal Cost:", total_cost)
   ```