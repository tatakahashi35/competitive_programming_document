# tsp
!!! Note
    未検証
``` c++
void tsp(Graph &graph){
    long long bits = pow(2, graph.number_of_vertice);
    vector<vector<long long>> min_dist(bits, vector<long long>(graph.number_of_vertice, INF)); // dp table, min_dist[行ったことある点集合][今いる点] = 最小距離
    for(long long i = 0 ; i < graph.number_of_vertice ; i++){
        min_dist[1LL<<i][i] = 0LL;
    }
    for(long long i = 0 ; i < bits ; i++){
        for(long long j = 0 ; j < graph.number_of_vertice ; j++){
            if((i>>j) & 1){
                // 行ったことある
            }else{
                // 行ったことないので、次に行く
                // 今いる場所
                vector<Edge> next_edges = graph.next(graph.vertice[k]);
                for(Edge &edge : next_edges){
                    // 行ったことある場所: i
                    // 今いる場所: k
                    // 行ったことない場所: j
                    // k -> j
                    min_dist[i + (1LL<<(edge.to))][j] = min(min_dist[i + (1LL<<(edge.to))][j], min_dist[i][edge.to] + distance_matrix[edge.to][j]);
            }
        }
    }
}
```
