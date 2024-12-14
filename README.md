# **Java Cheat Sheet for DSA and Competitive Programming**

This cheat sheet covers essential classes, methods, and utilities in Java for solving Data Structures and Algorithms (DSA) problems and competitive programming challenges. It is organized into sections for easy reference.

---

## **1. Input and Output**

### **1.1 Fast Input (BufferedReader and StringTokenizer)**
- **Reading Input:**
  ```java
  import java.io.*;
  import java.util.*;

  BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
  int n = Integer.parseInt(br.readLine());
  StringTokenizer st = new StringTokenizer(br.readLine());
  int[] arr = new int[n];
  for (int i = 0; i < n; i++) {
      arr[i] = Integer.parseInt(st.nextToken());
  }
  ```

- **Output:**
  ```java
  PrintWriter pw = new PrintWriter(System.out);
  pw.println("Output here");
  pw.flush();
  ```

### **1.2 Scanner Class (Easier but Slower)**
- **Reading Input:**
  ```java
  import java.util.*;

  Scanner sc = new Scanner(System.in);
  int n = sc.nextInt();
  int[] arr = new int[n];
  for (int i = 0; i < n; i++) {
      arr[i] = sc.nextInt();
  }
  sc.close();
  ```

### **1.3 Single-Line Input for Arrays**
- **Using `split` Function:**
  ```java
  String input = br.readLine();
  int[] arr = Arrays.stream(input.split(" "))
                    .mapToInt(Integer::parseInt)
                    .toArray();
  ```

### **1.4 Input Using Streams (Advanced)**
  ```java
  int[] arr = new BufferedReader(new InputStreamReader(System.in))
                 .lines()
                 .limit(n)
                 .mapToInt(Integer::parseInt)
                 .toArray();
  ```

---

## **2. Arrays**

### **2.1 Declaration and Initialization**
- **Single-Dimensional:**
  ```java
  int[] arr = new int[10];
  int[] arr = {1, 2, 3, 4, 5};
  ```
- **Multi-Dimensional:**
  ```java
  int[][] matrix = new int[3][3];
  ```

### **2.2 Utility Methods (`java.util.Arrays`)**
| Method                           | Description                                 |
|----------------------------------|---------------------------------------------|
| `Arrays.sort(arr)`               | Sorts the array in ascending order.         |
| `Arrays.binarySearch(arr, key)`  | Finds index of key in a sorted array.       |
| `Arrays.fill(arr, value)`        | Fills array with a specific value.          |
| `Arrays.toString(arr)`           | Converts array to a string.                 |
| `Arrays.equals(arr1, arr2)`      | Checks if two arrays are equal.             |

### **2.3 Multi-Dimensional Array Sorting**
- **Custom Sort Example:**
  ```java
  Arrays.sort(matrix, (a, b) -> Integer.compare(a[0], b[0]));
  ```

---

## **3. Collections Framework**

### **3.1 Key Classes**
#### **ArrayList**
| Method             | Description                           |
|--------------------|---------------------------------------|
| `add(element)`     | Adds an element.                     |
| `remove(index)`    | Removes the element at the index.    |
| `get(index)`       | Returns the element at the index.    |
| `size()`           | Returns the size of the list.        |
| `contains(element)`| Checks if the list contains an item. |
| `clear()`          | Removes all elements from the list.  |
| `isEmpty()`        | Checks if the list is empty.         |

#### **HashSet**
| Method             | Description                           |
|--------------------|---------------------------------------|
| `add(element)`     | Adds an element.                     |
| `remove(element)`  | Removes the element.                 |
| `contains(element)`| Checks if an element exists.         |
| `size()`           | Returns the size of the set.         |
| `isEmpty()`        | Checks if the set is empty.          |
| `clear()`          | Removes all elements from the set.   |

#### **HashMap**
| Method               | Description                           |
|----------------------|---------------------------------------|
| `put(key, value)`    | Adds or updates a key-value pair.    |
| `get(key)`           | Returns the value for the key.       |
| `remove(key)`        | Removes the key-value pair.          |
| `containsKey(key)`   | Checks if the map contains the key.  |
| `containsValue(value)`| Checks if the map contains the value.|
| `keySet()`           | Returns a set of keys.               |
| `values()`           | Returns a collection of values.      |
| `entrySet()`         | Returns a set of key-value pairs.    |
| `clear()`            | Removes all mappings.                |

#### **PriorityQueue**
| Method               | Description                           |
|----------------------|---------------------------------------|
| `add(element)`       | Adds an element.                     |
| `peek()`             | Retrieves, but does not remove, the head. |
| `poll()`             | Retrieves and removes the head.      |
| `remove(element)`    | Removes a specific element.          |
| `size()`             | Returns the size of the queue.       |
| `isEmpty()`          | Checks if the queue is empty.        |

---

## **4. String Handling**

### **4.1 Commonly Used String Methods**
| Method                          | Description                                |
|---------------------------------|--------------------------------------------|
| `charAt(index)`                 | Returns the character at the index.       |
| `substring(start, end)`         | Returns a substring.                      |
| `split(regex)`                  | Splits the string based on a delimiter.   |
| `replace(oldChar, newChar)`     | Replaces all occurrences of a character.  |
| `toCharArray()`                 | Converts the string to a char array.      |
| `length()`                      | Returns the length of the string.         |
| `indexOf(char)`                 | Finds the index of a character.           |
| `toLowerCase()`                 | Converts string to lowercase.             |
| `toUpperCase()`                 | Converts string to uppercase.             |

---

## **5. Streams (Java 8)**

### **5.1 Stream Operations**
| Method                          | Description                                |
|---------------------------------|--------------------------------------------|
| `stream().sorted()`             | Sorts the stream.                         |
| `stream().filter(predicate)`    | Filters based on a condition.             |
| `stream().map(function)`        | Applies a function to all elements.       |
| `stream().distinct()`           | Removes duplicate elements.               |
| `stream().forEach(action)`      | Performs an action on each element.       |
| `stream().collect(Collectors.toList())` | Collects stream into a list.       |
| `stream().anyMatch(predicate)`  | Returns true if any element matches.      |
| `stream().allMatch(predicate)`  | Returns true if all elements match.       |
| `stream().noneMatch(predicate)` | Returns true if no elements match.        |

### **5.2 Examples**
- **Filter and Sort:**
  ```java
  List<Integer> evenNumbers = list.stream()
                                  .filter(x -> x % 2 == 0)
                                  .sorted()
                                  .collect(Collectors.toList());
  ```

- **Sum Using Streams:**
  ```java
  int sum = Arrays.stream(arr).sum();
  ```

- **Group By Example:**
  ```java
  Map<Integer, List<String>> groupedByLength = strings.stream()
                                                       .collect(Collectors.groupingBy(String::length));
  ```

---

## **6. PriorityQueue (Heap)**

### **6.1 Min-Heap (Default)**
  ```java
  PriorityQueue<Integer> pq = new PriorityQueue<>();
  pq.add(10);
  pq.add(5);
  pq.add(20);
  System.out.println(pq.poll()); // Outputs smallest element
  ```

### **6.2 Max-Heap**
  ```java
  PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());
  pq.add(10);
  pq.add(5);
  pq.add(20);
  System.out.println(pq.poll()); // Outputs largest element
  ```

---

## **7. Algorithms Utilities**

### **7.1 GCD (Greatest Common Divisor)**
  ```java
  int gcd(int a, int b) {
      return b == 0 ? a : gcd(b, a % b);
  }
  ```

### **7.2 Sieve of Eratosthenes**
  ```java
  boolean[] sieve(int n) {
      boolean[] isPrime = new boolean[n + 1];
      Arrays.fill(isPrime, true);
      isPrime[0] = isPrime[1] = false;
      for (int i = 2; i * i <= n; i++) {
          if (isPrime[i]) {
              for (int j = i * i; j <= n; j += i) {
                  isPrime[j] = false;
              }
          }
      }
      return isPrime;
  }
  ```

---

This cheat sheet provides a comprehensive set of utilities for Java programming in competitive scenarios. Let me know if additional examples or methods are needed!

