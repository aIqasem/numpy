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
    
<br>

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

<br>

> ***How are lists different from NumPy***
> 
- **For Lists .. we can do Insertion, Deletion, Appending, Concatenation...**
- **NumPy supports all of these things + lots More (wait and see the following)**
    
    ---

<br> 

> ***Applications Of NumPy***
> 
- **Mathematics (MATLAB Replacement)**
- **Plotting (Matplotlib)**
- **Back-end (Pandas, Connect4, Digital Photography)**
- **Machine Learning**
    
    ---

<br>

### Complete Content on _[notion](https://darkened-fireman-c50.notion.site/NumPy-Basics-2d9334d3099747c395f455c6f3c836d6)_