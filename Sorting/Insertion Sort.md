CLRS INSERTION SORT
```
void insertionsort(int A[], int n)
{   
    if(n==1) return;
    int key,j,i;
    for(int j=1;j<=n-1;j++)
    {
        key=A[j];
        i=j-1;
        while(i>=0 && A[i]>key)
        {
            A[i+1]=A[i];
            i--;
        }
        A[i+1]=key;
        
    }// for ends  
}
```
2.1-2
Nonincreasing order insertion sort 
```
void insertionsort(int A[], int n)
{   
    if(n==1) return;
    int key,j,i;
    for(int j=1;j<=n-1;j++)
    {
        key=A[j];
        i=j-1;
        while(i>=0 && A[i]<key)
        {
            A[i+1]=A[i];
            i--;
        }
        A[i+1]=key;
        
    }// for ends  
}
```
