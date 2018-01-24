First fib using dictionaries 
Memoized DP Algorithm
```
memo={}
def fib(n):
    if n in memo:
        return memo[n]
    elif n<=2:
        memo[n]=1 
        return 1 # -*- coding: latin-1 -*-
    else:
        f=fib(n-1)+fib(n-2)
        memo[n]=f
        return f
        
```		

Memorized DP 2: Bottom-up version
```
memo={}
def fib(n):
    for i in range(1,n+1):
        if n<=2:
            f=1
        else:
            f=memo[n-1]+memo[n-2]
        memo[n]=f
    return memo[n]
```    
    
Space optimized fibonacci:

```
def fibonacci(n):
    a = 0
    b = 1
    if n < 0:
        print("Incorrect input")
    elif n == 0:
        return a
    elif n == 1:
        return b
    else:
        for i in range(2,n):
            c = a + b
            a = b
            b = c
        return b
```        
