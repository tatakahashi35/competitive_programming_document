# segment tree
!!! Note
    未検証
``` c++
class SegmentTree{
public:
    long long n; // 対象となる配列の要素数
    long long n_0_filled; // 対象となる配列の要素数 (0埋め分後)
    long long node; // segment tree の要素数
    vector<long long> tree;

    SegmentTree(long long N){
        n = N;
        long long d = (long long)(ceill(log2(n)));
        n_0_filled = pow(2, d);
        node = 2 * n_0_filled - 1;
        tree = vector<long long>(node, 0);
    }

    void init(std::vector<long long> &A){
        for(int i = 0; i < n; ++i){
            update(i, A[i]);
        }
    }

    // 要修正
    long long update_calculation(long long a, long long b){
        // 要素に対する計算
        return min(a, b);
    }

    void update(long long index, long long value){
        index = node - n_0_filled + index;
        tree[index] = update_calculation(tree[index], value);
        while(index > 0){
            index = (index - 1) / 2;
            tree[index] = query_calculation(index * 2 + 1, index * 2 + 2);
        }
    }

    // 要修正
    long long query_calculation(long long a, long long b){
        // 範囲に対する計算
        return min(a, b);
    }

    long long query(long long a, long long b){
        // l 以上 r 未満の区間に対して query_calculation() の結果を求める
        return query_sub(a, b, 0, 0, n_0_filled);
    }

    long long query_sub(long long a, long long b, long long k, long long l, long long r){
        if(r <= a || b <= l){
            // 区間外を含んでいる
            return 0;
        }else if(a <= l && r <= b){
            return tree[k];
        }else{
            long long left_value = query_sub(a, b, 2 * k + 1, l, (l + r) / 2);
            long long right_value = query_sub(a, b, 2 * k + 2, (l + r) / 2, r);
            return query_calculation(left_value, right_value);
        }
    }
};
```
