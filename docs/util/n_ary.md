# N進数

### 10 進数 → N 進数
``` c++
vector <long long> to_N_ary(long long X, long long N){
    // 10 進数の X を N 進数に変換する
    vector<long long> N_ary;
    while(X > 0){
        N_ary.push_back(X % N);
        X /= N;
    }
    reverse(N_ary.begin(), N_ary.end());
    return N_ary;
```

### N 進数 → 10 進数
!!! Note
    未検証
``` c++
vector<long long> to_decimal(vector<long long> N_ary, long long N){
    // N 進数の N_ary を 10 進数に変換する
    long long N_ary_10 = 0;
    reverse(N_ary.begin(), N_ary.end());
    for(auto num : N_ary){
        N_ary_10 = N_ary_10 * N + num;
    }
    return N_ary_10;
```

### vector 表記された数字の比較
``` c++
bool compare_vector_num(vector<long long> a, vector<long long> b){
    // a < b なら true
    // そうでないなら false
    if(a.size() < b.size()){
        return true;
    }else if(a.size() > b.size()){
        return false;
    }else{
        for(int i = 0; i < a.size(); ++i){
            if(a[i] < b[i]){
                return true;
            }else if(a[i] > b[i]){
                return false;
            }
        }
        return false;ß
    }
```