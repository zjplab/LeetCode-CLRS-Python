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
    
    
