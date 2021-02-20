# math

### floor
``` c++
(long long)(floor(1.5))
```

### ceil
``` c++
(long long)(ceil(1.5))
```

### sqrt
``` c++
sqrt(2.5)
```

### log
``` c++
log(2.5)
log2(2.5)
log10(2.5)
```

### 点と直線の距離
ax + by + c = 0 と (x0, y0) の距離
``` c++
long double dist = abs(a * x0 + b * y0 + c) / sqrt(a * a + b * b);
```
