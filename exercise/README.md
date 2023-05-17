## simple exercises

### _Create Array_

- `(1)`<br>
    import numpy.<br>

- `(2)`<br>
    Create a one dimensinoal array that contains numbers from 1 to 10.<br>

- `(3)`<br>
    Create the following array.<br>
    `[[15, 12, 9, 22],`<br>
    `[21, 7, 10, 14], `<br>
    `[31, 10, 33, 8]] `<br>

- `(4)`<br>
    Create an array full of zeros and of shape (2,3).

- `(5)`<br>
    Create an array that contains odd numbers from 1 to 1000.

---

<br>

### _Array Details_

- `(6)`<br>
    Start by making any 3D array.<br>

- `(7)`<br> 
    Show what `ndim` do.<br>

- `(8)`<br> 
    What is the difference between shape and size?<br>
    Explain with words and with code.<br>

---

<br>

### _Indexing & Slicing_

- `(9)`<br>
    Get the value of the element in the first row and second column.<br>

    ```
    np.random.seed(42)
    arr = np.random.randn(3, 3)
    # write your code here
    ```

- `(10)`<br>
    Get the first 2 rows.<br>

    ```
    np.random.seed(42)
    arr = np.random.randn(3, 3)
    # write your code here

    ```

- `(11)`<br>
    Change the shape of the array to be (2, 6) and print the new shape.<br>

    ```
    np.random.seed(42)
    arr = np.random.randn(4, 3)
    # write your code here
    ```

---

<br>

### _NumPy common functions_

- `(12)`<br> 
    Flat the following array.<br>

    ```
    arr = np.array([[i, 2*i, 3*i] for i in range(3, 300)])
    # write your code here
    ```

- `(13)`<br>
     Transpose the following array.<br>
     
     ```
     arr = np.array([[[[j, j + 1] for j in range(5)]] for i in range(3)])
    # write your code here
    ```

- `(14)`<br>
     How many unique values are in the following array and print them.<br>

     ```
     countries = np.array(['canada','spain','india','usa','canada','england','japan','germany','india','england','egypt','england','japan','egypt','india','japan'
                     ,'china','germany','india','china','canada','india','canada''egypt','china','germany','japan','russia'
                    ,'england','usa','germany','china','russia''germany''china','spain''spain','canada','germany','spain',
                    'china','canada','china''canada','germany','russia','japan','india','russia','egypt', 'canada',
                    'spain','india','usa','canada','england','japan','germany','india','england','egypt','england','japan',
                    'egypt','india','japan','china','germany','india','china','canada','india','canada''egypt','china','germany','japan','russia'
                      ,'england','usa','germany','china','russia''germany''china','spain''spain','canada','germany','spain',
                      'china','canada','china''canada','germany','russia','japan','india','russia','egypt'])
    # write your code here
    ```

- `(15)`<br> 
    Sort the following array.<br>
    
    ```
    np.random.seed(42)
    arr = np.random.randn(50)
    # write your code here
    ```

---

<br>

### _Statistics_

- `(16)`<br> Calculate the following.<br>

    ```
    np.random.seed(42)
    arr = np.random.randn(5,4)
    # write your code here
    # mean = 
    # median = 
    # sum =
    # variance = 
    # std = 
    ```

---

<br>

### _Maths_

- `(17)`<br>
     Calculate the following.<br>

     ```
     np.radnom.seed(42)
    arr = np.random.randn(5, 4)
    # max = 
    # min = 
    # sqrt = 
    # abs = 
    ```

- `(18)`<br>
    What is the difference between np.dot() & np.multiply() & np.matmul.<br>
    Explain with words and with code.<br>

    ```
    import numpy as np
    matrix1 = np.array([[1, 2], [3, 4]])
    matrix2 = np.array([[-1, 0], [-2, 4]])
    # write your code here
    ```

---
