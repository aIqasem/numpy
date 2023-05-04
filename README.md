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
    

> ***Some Coding***
> 
- ***Basic NumPy***
    - **creating a numpy array**
        
        ```python
        a = np.array([1,2,3,4,5])
        b = arr2 = np.array([[9.0,8.0,7.0], [6.0,5.0,4.0]])
        ```
        
        ---
        
    
    - **Dimensions**
        
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
        
    
    - **Shape**
        
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
        
    - **Data Type**
        
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
        
        - **To Change the data type of a numpy array**
        
        ```python
        c = np.array([1,2,3], dtype='int16')
        print(c.dtype)
        ```
        
        ```
        int16
        ```
        
        ---
        
    
    - **Size (in bytes)**
        
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
        
    
    - **Number of elements**
        
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
        
    
    - **Total size (in bytes)**
        
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
    - **Creating our array**
        
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
        
    
    - **Get an element** `[r,c]`
        
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
        
    - **Get a row** `[r,:]`
        
        ```python
        print(a[0,:])
        ```
        
        ```
        [1 2 3 4 5 6 7]
        ```
        
        ---
        
    - **Get a column**
        
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
        
    
    - **Change a column**
        
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
        
    - **Array of Array of vectors**
        
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
        
        - **Get elements**
        
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
    - Array of zeros - ones - some other value
        
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
        

- Random decimal
    
    ```python
    a = np.random.rand(2,3)
    print(a)
    ```
    
    ```
    [[0.32903081 0.05373669 0.17231712]
     [0.25423816 0.5425841  0.6214635 ]]
    ```
    
    ---
    

- Random int `(start,end,size())`, start is 0 by default, end in exclusive
    
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
    
- The Identity matrix
    
    ```python
    print(np.identity(3))
    ```
    
    ```
    [[1. 0. 0.]
     [0. 1. 0.]
     [0. 0. 1.]]
    ```
    
    ---
    
- Repeating
    
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
    
    ![array.png](https://github.com/aIqasem/numpy/blob/main/array.png)
    
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
    

> Stopped [*here*](https://youtu.be/QUT1VHiLmmI?t=1898) at $*31 \; of \;  58 \; mins*$
>