# util

### min
!!! Note
    未検証
``` c++
template<class T>
T my_min(T head, T next){
    return min(head, next);
}

template <class T, class... T>
T my_min(T head, T... body){
    return min(head, my_min(body...));
}
```

### max
!!! Note
    未検証
``` c++
template<class T>
T my_max(T head, T next){
    return max(head, next);
}

template <class T, class... T>
T my_max(T head, T... body){
    return max(head, my_max(body...));
}
```

### index_sort
!!! Note
    未検証
``` c++
bool comp(int i, int j) {
    return vec[i] < vec[j]
}

vector<long long> vec(N); // sort target
vector<long long> index(N);
iota(index.begin(), index.end(), 0);
sort(index.begin(), index.end(), comp);
```

### 出力
``` c++
printf("%lld\n", answer);
```
