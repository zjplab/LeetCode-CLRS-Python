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
int
BinarySearch (int a[], int low, int high, int key)
{
    int mid;

    if (low == high)
        return low;

    mid = low + ((high - low) / 2);

    if (key > a[mid])
        return BinarySearch (a, mid + 1, high, key);
    else if (key < a[mid])
        return BinarySearch (a, low, mid, key);

    return mid;
}
 
void
BinaryInsertionSort (int a[], int n)
{
    int ins, i, j;
    int tmp;

    for (i = 1; i < n; i++) {
        ins = BinarySearch (a, 0, i, a[i]);
        if (ins < i) {
            tmp = a[i];
            for (j = i - 1; j >= ins; j--)
                a[j + 1] = a[j];
            a[ins] = tmp;
        }
      
    }
}
```

using memmove():
```
void
BinaryInsertionSort (int a[], int n)
{
    int ins, i, j;
    int tmp;

    for (i = 1; i < n; i++) {
        ins = BinarySearch (a, 0, i, a[i]);
        if (ins < i) {
            tmp = a[i];
            memmove (a + ins + 1, a + ins, sizeof (int) * (i - ins));
            a[ins] = tmp;
        }
    }
}
```

Non-recursion:
```
void
BinaryInsertionSort (int a[], int n)
{
    register int i, m;
    int hi, lo, tmp;

    for (i = 1; i < n; i++) {
        lo = 0, hi = i;
        m = i / 2;

        do {
            if (a[i] > a[m]) {
                lo = m + 1;
            } else if (a[i] < a[m]) {
                hi = m;
            } else
                break;

            m = lo + ((hi - lo) / 2);
        } while (lo < hi);
 
        if (m < i) {
            tmp = a[i];
            memmove (a + m + 1, a + m, sizeof (int) * (i - m));
            a[m] = tmp;
        }
    }
}
```
