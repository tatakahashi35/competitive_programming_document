# graph
!!! Note
    未検証
``` c++
class Vertex{
public:
    long long id;
    long long weight; // 点重み
    long long distance; // ここまでの距離
    bool visited;

    Vertex(long long i, long long w){
        id = i;
        weight = w;
        distance = 0LL;
        visited = false;
    }

    Vertex(long long i){
        Vertex(i, 0LL);
    }

    bool operator<(const Vertex &v) const{
        // distance で比較
        if(distance < v.distance){
            return true;
        }else if(distance > v.distance){
            return false;
        }else{
            if(id < v.id){
                return true;
            }else if(id > v.id){
                return false;
            }else{
                return false;
            }
        }
    }

    bool operator==(const Vertex &v) const{
        if(id == v.id){
            return true;
        }
        return false;
    }

    inline bool operator!=(const Vertex& v) const{
        return !(*this == v);
    }
};

class Edge{
    static long long id_count;

public:
    long long id;
    long long from, to;
    long long weight; // 枝重み

    Edge(long long f, long long t, long long w){
        id = id_count++;
        from = f;
        to = t;
        weight = w;
    }

    Edge(long long f, long long t){
        Edge(f, t, 1LL);
    }

    bool operator<(const Edge &e) const{
        if(weight < e.weight){
            return true;
        }else if(weight > e.weight){
            return false;
        }else{
            if(from < e.from){
                return true;
            }else if(from > e.from){
                return false;
            }else{
                if(to < e.to){
                    return true;
                }else if(to > e.to){
                    return false;
                }else{
                    return false;
                }
            }
        }
    }

    bool operator==(const Edge &e) const{
        if(id == e.id){
            return true;
        }
        return false;
    }

    inline bool operator!=(const Edge& e) const{
        return !(*this == e);
    }
};

long long Edge::id_count = 0;

class Graph{
public:
    long long number_of_vertice;
    long long number_of_edges;
    vector<Vertex> vertice;
    vector<vector<Edge>> edges; // 隣接リスト

    Graph(long long N, long long M){
        number_of_vertice = N;
        number_of_edges = M;
        vertice.resize(N);
        edges.resize(N);
    }

    vector<Edge> next(Vertex vertex){
        // 隣接枝リストを返す
        return edges[vertex.id];
    }
};
```
