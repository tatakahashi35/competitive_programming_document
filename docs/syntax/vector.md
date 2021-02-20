# vector

### initialize
``` c++
// N行M列の二次元vectorの宣言
vector<vector<long>> edges(N, vector<long>(M, 0));
// 3次元
vector<vector<vector<long>>> data(N, vector<vector<long>>(M, vector<long>(K)));

// 初期化
vector<vector<long>> edges(N, vector<long>(M, 0));

// 同じ値で埋める
fill(vec.begin(),vec.end(), 3);

// 連番
iota(vec.begin(), vec.end(), 0);
```

### for
- 参照
``` c++
for(auto v : vec){
    cout<<v<<" ";
}
cout<<endl;
```

- 代入
``` c++
for(auto &v : vec){
    v = v * 2;
}
```

### max, min
``` c++
auto max_itr = max_element(vec.begin(), vec.end());
auto min_itr = min_element(vec.begin(), vec.end());
```

### sort
``` c++
sort(vec.begin(), vec.end());
```

### reverse
``` c++
reverse(vec.begin(), vec.end());
```

### accumulate
- sum
``` c++
accumulate(vec.begin(), vec.end(), 0);
```
- 文字列連結
``` c++
accumulate(vec.begin(), vec.end(), string());
```
- 任意の二項演算 (初期値を 1 に設定)
``` c++
accumulate(vec.begin(), vec.end(), 1, [](int acc, int i) {
    return acc * i; // Π (全要素の積)
});
```

### binary search
``` c++
// 第3引数以上になる最初の要素を指すイテレータを返す
lower_bound(vec.begin(), vec.end(), 123);

// 第3引数より大きくなる最初の要素を指すイテレータを返す
upper_bound(vec.begin(), vec.end(), 123);

// 第3引数が存在するかを表すboolを返す
binary_search(vec.begin(), vec.end(), 123);
```

### index を返す
``` c++
auto itr = find(vec.begin(), vec.end(), 123);
int index = distance(vec.begin(), itr);
```
