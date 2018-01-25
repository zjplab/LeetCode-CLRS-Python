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

Binary Insertion Sort
```
int binarySearch(int a[], int item, int low, int high)
{
    if (high <= low)
        return (item > a[low])?  (low + 1): low;
 
    int mid = (low + high)/2;
 
    if(item == a[mid])
        return mid+1;
 
    if(item > a[mid])
        return binarySearch(a, item, mid+1, high);
    return binarySearch(a, item, low, mid-1);
}
 
// Function to sort an array a[] of size 'n'
void insertionSort(int a[], int n)
{
    int i, loc, j, k, selected;
 
    for (i = 1; i < n; ++i)
    {
        j = i - 1;
        selected = a[i];
 
        // find location where selected sould be inseretd
        loc = binarySearch(a, selected, 0, j);
 
        // Move all elements after location to create space
        while (j >= loc)
        {
            a[j+1] = a[j];
            j--;
        }
        a[j+1] = selected;
    }
}
```
