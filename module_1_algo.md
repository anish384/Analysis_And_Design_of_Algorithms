```
Module-1:
    1. Introduction:
        ○ Chapter 1:
            § Section 1.1: What is an Algorithm?
            § Section 1.2: Fundamentals of Algorithmic Problem Solving
    2. Fundamentals of the Analysis of Algorithm Efficiency:
        ○ Chapter 2:
            § Section 2.1: Analysis Framework
            § Section 2.2: Asymptotic Notations and Basic Efficiency Classes
            § Section 2.3: Mathematical Analysis of Non-recursive Algorithms
            § Section 2.4: Mathematical Analysis of Recursive Algorithms
    3. Brute Force Approaches:
        ○ Chapter 3:
            § Section 3.1: Selection Sort and Bubble Sort
            § Section 3.2: Sequential Search
            § Section 3.3: Brute Force String Matching
```

# C++ Codes
---
## Sieve of Eratosthenes
---
```c 
#include <bits/stdc++.h>
using namespace std;

vector<int> Sieve(int n)
{
    /*
    *
    * Implements Sieve of Eratosthenes
    * Input  : Positive integer n > 1
    * Output : Vector which contains all the prime number up to n
    *
    */ 
    
    vector<int> a;
    vector<int> ans;
    for(int i = 0; i <=n; i++){
        a.push_back(i);
    }
    int j = 0;
    a[0] = a[1] = 0;
    for(int i = 0; i <= sqrt(n); i++){
        if(a[i] != 0){
            j = i * i;
            while(j <= n){
                a[j] = 0;
                j = j + i;
            }
        }
    }

    for(int i = 0; i <= a.size(); i++){
        if(a[i] != 0){
            ans.push_back(a[i]);
        }
    }

    return ans;
}

int main()
{
    vector<int> v;
    v = Sieve(20);
    for(auto &x: v){
        cout<<x<<' ';
    }
}
```

## Euclid's Algorithm for computing gcd(m,n)
---
```c 
#include <bits/stdc++.h>
using namespace std;
int gcd(int m, int n){
    /* 
     *
        Computes gcd(m,n) by Euclid's Algorithm
        Input  : two nonnegative, not both zero m and n 
        Output : gcd of m and n
    *
    */
    while(n != 0){
        int r = m % n;
        m = n;
        n = r;
    }
    return m;
}

int main()
{
    int m,n;
    cin>>m>>n;
    int ans = gcd(m,n);
    cout<<ans<<'\n';
}
```

## Selection Sort Algorithm
---
```c 
void selection_sort(vector<int> &v){
    int n = v.size();
    int i,j;
    int min;
    for(i=0; i < n-1; i++){
        min = i;
        for(j = i+1; j < n; j++){
            if(v[j] < v[min]) min = j;
        }
        swap(v[i],v[min]);
    }
}

int main()
{
    vector<int> v {5,4,3,2,1};
    selection_sort(v);
    for(auto &x: v){
        cout<<x<<' ';
    }
}
```

---
