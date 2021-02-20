# string

### substr
``` c++
s = "hogehoge";
s.substr(1, 3); // "oge"
```

### int → string 変換
``` c++
ll num = 123;
to_string(num);
```

### char → string 変換
!!! Note
    未検証
``` c++
auto a = std::string() + 'a'; // "a"
auto b = ""s + 'b'; // "b" (C++14)
```

### 大文字判定
``` c++
isupper(c); // 大文字なら true
```

### 検索
``` c++
string word = "word";
if (str.find(word) == string::npos){
    // みつからなかった
}else{
    // みつかった
}
```