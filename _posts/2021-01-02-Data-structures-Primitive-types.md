---
layout:     post
title:      Data Structures - Primitive Types
subtitle:   
date:       2021-01-02
author:     R.
header-img: 
catalog: true
tags:
    - Data Structure
---

# Primitive Types:

In Python, everything is an object, including Booleans, ints, chars 
```python
def count_bits(x):
    num_bits = 0
    while x:
        num_bits += x & 1
        x >>= 1
    return num_bits
```
'>>' and '<<' in python is bit operator, it moves the number(binary) to left or right for digits 

* Build-in types in Python: 
    - numerics  
    - sequences 
    - mappings 
    - classes
    - instances 
    - exceptions 

python3 ints are unbounded 

- & 与 | 为 位上的 and  or
```python
2 & 3   ---> 10 & 11 = 10(base 2) = 2 
1 & 0   ---> 10 & 01 = 0 
```
^ is XOR
a 与 b 不一样 --- ture
a 与 b 一样   --- false
```python
2 ^ 3 = 1
```

~ 按位取反
```python
~8 = 7 
```
