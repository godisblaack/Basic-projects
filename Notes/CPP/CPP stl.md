# C++ Standard Template Library

## Containers

### Vector (Dynamic Array)

#### Syntax

```cpp
vector<int> vectorName = {1, 2, 3, 4}; // Initialization is optional
```

```cpp
vector<int> vectorName(size, valueAtEveryIndex); // e.g., vector<int> vectorName(3, 10) creates a vector of size 3 with each index storing value 10.
```

```cpp
vector<int> vector1 = {1, 2, 3};
vector<int> copyVector1(vector1);
```

#### Description

A vector's capacity doubles when it gets full. Data from the old vector is copied into a new vector that is double the size of the old vector.
Vectors have two properties:
1. **Size**: The number of elements currently present in the vector.
2. **Capacity**: The total number of elements a vector can hold before it needs to resize.

#### Functions

1. `size()`: Returns the number of elements in the vector.
2. `capacity()`: Returns the current capacity of the vector.
3. `push_back(dataToBePushed)`: Adds an element to the end of the vector.
4. `pop_back()`: Removes the last element of the vector.
5. `emplace_back()`: Constructs an element in-place and adds it to the end of the vector (more efficient than push_back for complex objects).
6. `at(indexNumber)`: Returns a reference to the element at the specified position.
7. `front()`: Returns a reference to the first element in the vector.
8. `back()`: Returns a reference to the last element in the vector.
9. `erase(startingIndex, endingIndex (optional))`: Removes elements in the specified range. Ending index is optional.

    ```cpp
    vectorName.erase(
        vectorName.begin() + indexNumber) // Removes elements from a specified location

    vectorName.erase(
        vectorName.begin() + indexNumber, 
        vectorName.begin() + indexNumber); // Removes elements from a specified range

    vectorName.erase(vectorName.begin(), vectorName.end()); // Removes all the elements
    ```

    Note: The `erase()` function changes the size of the vector, not its capacity.

10. `insert(indexNumber, value)`: Inserts an element at the specified position.

    ```cpp
    vectorName.insert(vectorName.begin() + indexNumber, value);
    ```

11. `clear()`: Removes all elements from the vector.
12. `empty()`: It returns a boolean value, 1 if the condition is `true` meaning the vector does not contain any element, and 0 if the condition is `false` meaning the vector have some value.

Note: The functions from 13 to 18 are known as vector iterators.

13. `begin()`: Returns an iterator to the first element of the vector.

    An iterator is an object that can be used like a pointer to traverse elements, but it isn't simply a raw pointer.

14. `end()`: Returns an iterator to the element following the last element of the vector, which acts as a boundary.

    Usage of iterator functions:

    ```cpp
    vector<int>::iterator i;
    for(i = vectorName.begin(); i != vectorName.end(); i++) {
        cout << *(i) << endl;
    }
    ```

    ```cpp
    for(vector<int>::iterator i = vectorName.begin(); i != vectorName.end(); i++) {
        cout << *(i) << endl;
    }
    ```

    ```cpp
    for(auto i = vectorName.begin(); i != vectorName.end(); i++) {
        cout << *(i) << endl;
    }
    ```

15. `rbegin()`: Returns a reverse iterator to the last element of the vector.

16. `rend()`: Returns a reverse iterator to the element preceding the first element of the vector.

    Usage of reverse iterator functions:

    ```cpp
    vector<int>::reverse_iterator i;
    for(i = vectorName.rbegin(); i != vectorName.rend(); i++) {
        cout << *(i) << endl;
    }
    ```

17. `cbegin()`: Returns a constant iterator to the first element of the vector.

18. `cend()`: Returns a constant iterator to the element following the last element of the vector.

    Usage of constant iterator functions:

    ```cpp
    vector<int>::const_iterator i;
    for(i = vectorName.cbegin(); i != vectorName.cend(); i++) {
        cout << *(i) << endl;
    }
    ```