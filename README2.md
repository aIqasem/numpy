# NumPy Basics

> ***What is NumPy* ?**
> 
- **It is a multi-dimensional array library**
- **You can use NumPy to store all sorts of data in**
    - One dimensional arrays
    - Two dimensional arrays
    - Three dimensional arrays
    - Four .. enough wasting time
    
    ---
    

> ***NumPy Over Lists***
> 
- **The main difference comes from the speed .. Lists are so slow while NumPy is so fast**
    - One reason for this is that NumPy uses fixed types .. the hole elements are int32 (default) .. you can specify them to int16 or even int8 (for a single byte) if you want to store really small values.
    - **Lists use a built-in int type for python .. and this built-in type consist of four different things**
        - Obj value .. which has its own bits (8 Bytes)
        - Obj type .. (8 Bytes)
        - Reference count .. how many times that that integer has been pointed at .. (8 Bytes)
        - Size of that integer value .. (almost 4 Bytes)
    - **When iterating through NumPy Objects, you don’t have to do type checking**
    - **NumPy uses [contiguous memory](https://drive.google.com/file/d/1nOpG5CmWddVbvlxyMj1HSOVfhydlqJ8-/view?usp=share_link)**
        - Benefits
            - SIMD Vector Processing (Single Instruction Multiple Data) .. when performing an addition operation on a lot of values .. instead of doing one addition at a time .. we can use the SIMD unit to perform computations on all of these values (stored in a NumPy) at the contiguous memory at one time.
            - Effective Cache Utilization .. we can load all values and keep them close to where we need to access them .. in List case .. you may load just the have of it (for instance)
- **So .. A single int in lists using the built-in int type requires a lot more space than NumPy**
    
    ---
    

> ***How are lists different from NumPy***
> 
- **For Lists .. we can do Insertion, Deletion, Appending, Concatenation...**
- **NumPy supports all of these things + lots More (wait and see the following)**
    
    ---
    

> ***Applications Of NumPy***
> 
- **Mathematics (MATLAB Replacement)**
- **Plotting (Matplotlib)**
- **Back-end (Pandas, Connect4, Digital Photography)**
- **Machine Learning**
    
    ---
    

> ***Some Basic Coding***
> 
> - [***Basic NumPy***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
> - [*****Mathematics*****](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
> - [*****Statistics*****](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
> - [*****Reorganizing arrays*****](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)

---

## ***Basic NumPy***

<aside>
<img src="NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/fast.png" alt="NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/fast.png" width="40px" /> ***Content** ( [Up](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md) )*

- [***creating a numpy array***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Dimensions***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Shape***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Data Type***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Size (in bytes)***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)

- [***Number of elements***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Total size (in bytes)***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Accessing - Changing specific elements, rows, columns, etc***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Initializing different types of arrays***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Copying arrays***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
</aside>

- ***creating a numpy array***
    
    ```python
    a = np.array([1,2,3,4,5])
    b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
    ```
    
    ---
    

- ***Dimensions***
    
    ```python
    a = np.array([1,2,3,4,5])
    b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
    
    print(a.ndim)
    print(b.ndim)
    ```
    
    ```
    1
    2
    ```
    
    ---
    

- ***Shape***
    
    ```python
    a = np.array([1,2,3,4,5])
    b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
    
    print(a.shape)
    print(b.shape)
    ```
    
    ```
    (5,)
    (2, 3)
    ```
    
    ---
    
- ***Data Type***
    
    ```python
    a = np.array([1,2,3,4,5])
    b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
    
    print(a.dtype)
    print(b.dtype)
    ```
    
    ```
    int64
    float64
    ```
    
    - To Change the data type of a numpy array
    
    ```python
    c = np.array([1,2,3], dtype='int16')
    print(c.dtype)
    ```
    
    ```
    int16
    ```
    
    ---
    

- ***Size (in bytes)***
    
    ```python
    a = np.array([1,2,3,4,5])
    b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
    c = np.array([1,2,3], dtype='int16')
    
    print(a.itemsize)
    print(b.itemsize)
    print(c.itemsize)
    ```
    
    ```
    8
    8
    2
    ```
    
    ---
    

- ***Number of elements***
    
    ```python
    a = np.array([1,2,3,4,5])
    b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
    c = np.array([1,2,3], dtype='int16')
    
    print(a.size)
    print(b.size)
    print(c.size)
    ```
    
    ```
    5
    6
    3
    ```
    
    ---
    

- ***Total size (in bytes)***
    
    ```python
    a = np.array([1,2,3,4,5])
    b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
    c = np.array([1,2,3], dtype='int16')
    
    print(a.size * a.itemsize)
    print(b.size * b.itemsize)
    print(c.size * c.itemsize)
    ```
    
    ```
    40
    48
    6
    ```
    
    - Another way
    
    ```python
    a = np.array([1,2,3,4,5])
    b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
    c = np.array([1,2,3], dtype='int16')
    
    print(a.nbytes)
    print(b.nbytes)
    print(c.nbytes)
    ```
    
    ```
    40
    48
    6
    ```
    
    ---
    

- ***Accessing - Changing specific elements, rows, columns, etc***
    - ***Creating our array***
        
        ```python
        a = np.array([[1,2,3,4,5,6,7],[8,9,10,11,12,13,14]])
        print(a)
        print(a.shape)
        ```
        
        ```
        [[ 1  2  3  4  5  6  7]
         [ 8  9 10 11 12 13 14]]
        
        (2, 7)
        ```
        
        ---
        
    
    - ***Get an element*** `[r,c]`
        
        ```python
        print(a[1,5])
        ```
        
        ```
        13
        ```
        
        - similar as lists, **you can use** **negative indexes** to start from the end
        
        ```python
        print(a[1,-2])
        ```
        
        ```
        13
        ```
        
        ---
        
    - ***Get a row*** `[r,:]`
        
        ```python
        print(a[0,:])
        ```
        
        ```
        [1 2 3 4 5 6 7]
        ```
        
        ---
        
    - ***Get a column***
        
        ```python
        b = np.array([3,10])
        c = a[:,2] ***# a column of array a***
        
        print(b)
        print(b.shape)
        
        print(c)
        print(c.shape)
        ```
        
        ```
        [ 3 10]
        (2,)
        
        [ 3 10]
        (2,)
        ```
        
        - Seems like it returns the elements of that column .. and puts it into a vector (1 row of elements)
        - To print it as a column (which is an array of vectors), try this:
        
        ```python
        print(a[:,2:4]) ***# column 3 and 4 of array a***
        ```
        
        ```
        [[ 3  4]
         [10 11]]
        ```
        
        - When printing several columns .. it is printed as we like to see .. columns as columns
        - To print one column .. try this trick
        
        ```python
        print(a[:,2:3]) ***# column 3 of array a***
        ```
        
        ```
        [[ 3]
         [10]]
        ```
        
        - Looks like a column .. remember .. the last element in the range is excluded so this works
        
        - Simple function to print a column in a vertical seen (array of vectors)
        
        ```python
        def print_column(a:np.array,index):
            print(a[:,index:index+1])
        ```
        
        ---
        
    
    - ***Change a column***
        
        ```python
        a[:,2] = 5 ***# This changes all column elemnts to 5***
        print(a)
        
        a[:,2] = [0,0]
        print(a)
        ```
        
        ```
        [[ 1  2  5  4  5  6  7]
         [ 8  9  5 11 12 13 14]]
        
        [[ 1  2  0  4  5  6  7]
         [ 8  9  0 11 12 13 14]]
        ```
        
        ---
        
    - ***Array of Array of vectors***
        
        ```python
        d3 = np.array([[[1,2],[3,4]],[[5,6],[7,8]]])
        
        print(d3)
        
        print(d3.shape)
        ```
        
        ```
        [[[1 2]
          [3 4]]
        
         [[5 6]
          [7 8]]]
        
        (2, 2, 2)
        ```
        
        - ***Get elements***
        
        ```python
        print(d3[0,0,0]) # 1
        print(d3[0,:,0]) # 1 3
        print(d3[1,0,:]) # 5 6
        ```
        
        ```
        1
        [1 3]
        [5 6]
        ```
        
        ---
        

- ***Initializing different types of arrays***
    - ***Array of zeros - ones - some other value***
        
        ```python
        a = np.zeros([2,3])
        print(a)
        
        b = np.ones([2,3])
        print(b)
        
        c = np.full([3,3],5)
        print(c)
        ```
        
        ```
        [[0. 0. 0.]
         [0. 0. 0.]]
        
        [[1. 1. 1.]
         [1. 1. 1.]]
        
        [[5 5 5]
         [5 5 5]
         [5 5 5]]
        ```
        
        ---
        
    
    - ***Random decimal***
        
        ```python
        a = np.random.rand(2,3)
        print(a)
        ```
        
        ```
        [[0.32903081 0.05373669 0.17231712]
         [0.25423816 0.5425841  0.6214635 ]]
        ```
        
        ---
        
    - ***Random int*** `(start,end,size())`***, start is 0 by default, end in exclusive***
        
        ```python
        a = np.random.randint(10, size=(3,3))
        print(a)
        ```
        
        ```
        [[3 0 5]
         [7 6 6]
         [7 2 7]]
        ```
        
        ---
        
    - ***The Identity matrix***
        
        ```python
        print(np.identity(3))
        ```
        
        ```
        [[1. 0. 0.]
         [0. 1. 0.]
         [0. 0. 1.]]
        ```
        
        ---
        
    - ***Repeating***
        
        ```python
        a = np.array([[1,2,3]])
        print(a)
        ```
        
        - *Note: ‘a’ is a multidimensional array to support applying repeating in axis 0 and 1 as following*
        
        ```
        [[1 2 3]]
        ```
        
        ```python
        r = np.repeat(a,3)
        print(r)
        ```
        
        ```
        [1 1 1 2 2 2 3 3 3]
        ```
        
        ```python
        r = np.repeat(a,3, axis = 0)
        print(r)
        ```
        
        ```
        [[1 2 3]
         [1 2 3]
         [1 2 3]]
        ```
        
        ---
        
    
    > ***Quiz***
    > 
    - Create this array
        
        ![Untitled](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/Untitled.png)
        
    - *Solution*
        
        ```python
        a = np.ones((5,5))
        a[1:-1,1:-1] = 0
        a[2,2] = 9
        print(a)
        ```
        
        ```
        [[1. 1. 1. 1. 1.]
         [1. 0. 0. 0. 1.]
         [1. 0. 9. 0. 1.]
         [1. 0. 0. 0. 1.]
         [1. 1. 1. 1. 1.]]
        ```
        
        ---
        
- ***Copying arrays***
    
    ```python
    a = np.array([1,2,3])
    b = a
    b[0] = 0
    
    print(a)
    ```
    
    ```
    [0 2 3]
    ```
    
    - Copying arrays like this doesn’t work, this just created some pointer to the memory storing the array
    - Copy arrays like this:
    
    ```python
    a = np.array([1,2,3])
    c = a.copy()
    c[1] = 50
    
    print(a)
    print(c)
    ```
    
    ```
    [1 2 3]
    [ 0 50  3]
    ```
    
    ---
    

## *****Mathematics*****

<aside>
<img src="NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/fast%201.png" alt="NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/fast%201.png" width="40px" /> ***Content** ( [Up](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md) )*

- [***Element-wise operation***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Take `sin` of all values***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)

- [***Linear algebra***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Find the determinant***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
</aside>

- ***Element-wise operation***
    
    ```python
    a = np.array([1,2,3,4,5])
    a += 2
    print(a)
    a -= 2
    print(a)
    a *= 2
    print(a)
    ```
    
    ```
    [3 4 5 6 7]
    [1 2 3 4 5]
    [ 2  4  6  8 10]
    ```
    
    ---
    
- ***Take `sin` of all values***
    
    ```python
    sins = np.sin(a)
    print(sins)
    ```
    
    ```
    [ 0.90929743 -0.7568025  -0.2794155   0.98935825 -0.54402111]
    ```
    
    ---
    
- ***Linear algebra***
    
    ```python
    a = np.ones((2,3))
    b = np.full((3,2), 2)
    
    print(a)
    print()
    print(b)
    np.matmul(a,b)
    ```
    
    ```
    [[1. 1. 1.]
     [1. 1. 1.]]
    
    [[2 2]
     [2 2]
     [2 2]]
    
    array([[6., 6.],
           [6., 6.]])
    ```
    
    ---
    
- ***Find the determinant***
    
    ```python
    a = np.identity(3)*3
    print(a)
    print()
    print(np.linalg.det(a))
    ```
    
    ```
    [[3. 0. 0.]
     [0. 3. 0.]
     [0. 0. 3.]]
    
    27.0
    ```
    
    ---
    

## *****Statistics*****

<aside>
<img src="NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/fast%202.png" alt="NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/fast%202.png" width="40px" /> ***Content** ( [Up](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md) )*

- [***min and max***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Get the min or max in a row or a column***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)

- [***Sum (all - row - columns)***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Mean and Median***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
</aside>

- ***min and max***
    
    ```python
    st = np.array([[1,2,3,4,5],[6,7,8,9,10]])
    np.max(st)
    np.min(st)
    ```
    
    ```
    10
    1
    ```
    
    ---
    
- ***Get the min or max in a row or a column***
    
    ```python
    st = np.array([[1,2,3,4,5],[6,7,8,9,10]])
    print(st)
    
    ***# max of each row***
    np.max(st, axis=1) 
    
    ***# max of each column***
    np.max(st, axis=0) 
    ```
    
    ```
    ***# st***
    array([[ 1,  2,  3,  4,  5],
           [ 6,  7,  8,  9, 10]])
    
    ***# max of each row***
    array([ 5, 10])
    
    ***# max of each column***
    array([ 6,  7,  8,  9, 10])
    ```
    
    ---
    
- ***Sum (all - row - columns)***
    
    ```python
    st = np.array([[1,2,3,4,5],[6,7,8,9,10]])
    print(st)
    ```
    
    ```
    array([[ 1,  2,  3,  4,  5],
           [ 6,  7,  8,  9, 10]])
    ```
    
    - *all elements*
    
    ```python
    np.sum(st)
    ```
    
    ```
    55
    ```
    
    - *sum of each row*
    
    ```python
    np.sum(st, axis=1)
    ```
    
    ```
    array([15, 40])
    ```
    
    - *sum of each column*
    
    ```python
    np.sum(st, axis=0)
    ```
    
    ```
    array([ 7,  9, 11, 13, 15])
    ```
    
    ---
    
- ***Mean and Median***
    
    ```python
    print(np.mean(st))
    print(np.median(st))
    ```
    
    ```
    5.5
    5.5
    ```
    
    ---
    

## *****Reorganizing arrays*****

<aside>
<img src="NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/fast%203.png" alt="NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6/fast%203.png" width="40px" /> ***Content** ( [Up](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md) )*

- [***Reshaping***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
- [***Vertically stacking vectors***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)

- [***Horizontal stacking***](NumPy%20Basics%202d9334d3099747c395f455c6f3c836d6.md)
</aside>

- ***Reshaping***
    
    ```python
    a = np.array([[1,2,3,4],[5,6,7,8]])
    print(a , "\n\n Shape:\n" , a.shape)
    ```
    
    ```
    [[1 2 3 4]
     [5 6 7 8]] 
    
     Shape:
     (2, 4)
    ```
    
    - Shaping should have the same number of elements that fits the new shape
    
    ```python
    after = a.reshape((8,1))
    print(after)
    ```
    
    ```
    [[1]
     [2]
     [3]
     [4]
     [5]
     [6]
     [7]
     [8]]
    ```
    
    ```python
    after = a.reshape((1,8))
    print(after)
    ```
    
    ```
    [[1 2 3 4 5 6 7 8]]
    ```
    
    ---
    
- ***Vertically stacking vectors***
    
    *works for same number of columns*
    
    ```python
    v1 = np.array([1,2,3,4])
    v2 = np.array([5,6,7,8])
    v_stack = np.vstack([v1,v2])
    
    print(v_stack)
    ```
    
    ```
    [[1 2 3 4]
     [5 6 7 8]]
    ```
    
    - *stacking `v1`,`v2`,`v_stack`*
    
    ```python
    v_another_stack = np.vstack([v1,v2,v_stack])
    print(v_another_stack)
    ```
    
    - *This works because v_stack has the same number of columns*
    
    ```
    [[1 2 3 4]
     [5 6 7 8]
     [1 2 3 4]
     [5 6 7 8]]
    ```
    
    - U can stack specific rows like this
    
    ```python
    v_another_stack = np.vstack([v1,v2,v_stack[0]])
    print(v_another_stack)
    ```
    
    ```
    [[1 2 3 4]
     [5 6 7 8]
     [1 2 3 4]]
    ```
    
    ---
    
- ***Horizontal stacking***
    
    *works for same number of rows*
    
    ```python
    v1 = np.array([1,2,3,4])
    v2 = np.array([5,6,7,8])
    v_stack = np.hstack([v1,v2])
    
    print(v_stack)
    ```
    
    ```
    [1 2 3 4 5 6 7 8]
    ```
    
    - *Stacking (same rows) different number of columns*
    
    ```python
    arr1 = np.ones((2,4))
    arr2 = np.zeros((2,2))
    
    print(arr1, "\n\n", arr2)
    ```
    
    ```
    [[1. 1. 1. 1.]
     [1. 1. 1. 1.]] 
    
     [[0. 0.]
     [0. 0.]]
    ```
    
    ```python
    h_stack = np.hstack([arr1,arr2])
    print(h_stack)
    ```
    
    ```
    [[1. 1. 1. 1. 0. 0.]
     [1. 1. 1. 1. 0. 0.]]
    ```
    
    ---
    

> ***Nice to see you***
>