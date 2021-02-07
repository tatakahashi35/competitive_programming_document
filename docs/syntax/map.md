## map

### initialize
``` c++
map<int, int> dic;
```

``` c++
map<int, int> dic{
    {1: 2},
    {3: 4},
    {5: 6},
};
```

### for
- 参照
``` c++
for (auto const& [key, value] : dic){
    cout<<key<<" "<<value<<endl;
}
```
