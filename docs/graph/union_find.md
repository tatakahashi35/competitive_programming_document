# union find
!!! Note
    未検証
``` c++
class UnionFind{
public:
    long long N;
    long long groups;
    vector<long long> parent;

    UnionFind(long long n){
        N = n;
        groups = N;

        parent.resize(N);
        iota(parent.begin(), parent.end(), 0);
    }

    long long get_parent(long long i){
        if(parent[i] < 0){
            return i;
        }
        return parent[i] = get_parent(parent[i]);
    }

    long long get_size(long long i){
        return -p[parent(i)];
    }

    void union_groups(long long a, long long b){
        a = parent(a);
        b = parent(b);
        if(a != b){
            if(p[a] > p[b]){
                swap(a, b);
            }
            p[a] += p[b];
            p[b] = a;
            groups--;
        }
    }
```

```
union_find = UnionFind(N);
```
