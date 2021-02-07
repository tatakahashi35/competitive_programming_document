# prime

### prime
!!! Note
    未検証
``` c++
vector<long long> calc_primes(long long n){
    // n 未満の素数を返す
    vector<long long> primes;

    if(n < 2){
        return primes;
    }

    // init
    vector<bool> prime_pool(n, true);
    prime_pool[0] = false;
    prime_pool[1] = false;
    long long upper = (long long)ceill(sqrtl(n))) + 1LL;

    long long k = 2;
    while(k < upper){
        while(k < upper){
            if(prime_pool[k]){
                // k: prime number
                primes.push_back(k);
                break;
            }
            k++;
        }
        long long next_prime = k;
        for(long long i = next_prime * next_prime; i < upper; i += next_prime){
            prime_pool[i] = true;
        }
        k++;
    }

    for(int i = primes[primes.size() - 1]; i < n; ++i){
        if(prime_pool[i]){
            primes.push_back(i);
        }
    }

    return primes;
```

### prime factor
!!! Note
    未検証
``` c++
map<long long> prime_factor(long long n){
    // 素因数分解
    vector<long long> primes = calc_primes(n + 1); // N + 1 未満の素数
    long long number_of_primes = primes.size();
    map<long, long> prime_factors;

    long long sqrt_n = (long long)ceill(sqrtl(n))) + 1LL;
    for(long long i = 0; i < number_of_primes; ++i){
        if(n == 1){
            break;
        }
        if(n % primes[i] == 0){
            n /= primes[i];
            prime_factors[primes[i]] = 1;
            while(n % primes[i] == 0){
                n /= primes[i];
                prime_factors[primes[i]]++;
            }
        }
    }
    return prime_factors;
}
```
