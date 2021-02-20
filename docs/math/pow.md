# pow
!!! Note
    未検証
``` c++
long long pow(long long a, long long n, long long m){
    if(n == 0){
        return 1LL;
    }else if(n == 1){
        return a % m;
    }else if(n % 2 == 0){
        long long b = pow(a, n / 2, m);
        return b * b % m;
    }else{
        return a * pow(a, n - 1, m) % m;
    }
}
```

``` c++
long double p = powl(a, n);
```
