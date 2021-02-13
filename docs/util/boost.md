# Boost

### range based for
!!! Note
    未検証
``` c++
using boost::irange;

for (int i : irange(0, N, 1)) {
    //
}
```

### 多倍長
!!! Note
    未検証
``` c++
using boost::multiprecision::cpp_int;

cpp_int N;
```

### split
!!! Note
    未検証
``` c++
using boost::algorithm::split;

string S;
vector<string> S_splited;
split(S_splited, S, boost::is_any_of(".")); // S を . 区切りしたものが S_splited に格納される
```

### join
!!! Note
    未検証
``` c++
using boost::algorithm::join;

vector<string> S
string s = join(S, " "); // S をスペース区切りで連結
```

### replace_all
!!! Note
    未検証
``` c++
using boost::algorithm::replace_all; // 破壊的
using boost::algorithm::replace_all_copy; // 非破壊的

replace_all(S, "ABC", "abc"); // ABC を abc に置換
string result = boost::algorithm::replace_all_copy(S, "ABC", "abc");
```

### argmin / argmax
!!! Note
    未検証
``` c++
using boost::math::tools::brent_find_minima;

cpp_int N;
```
