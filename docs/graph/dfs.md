# dfs
!!! Note
    未検証
``` c++
void dfs(long long vertex_id, Graph &graph){
    Vertex start = graph.vertice[vertex_id];
    start.visited = true;

    vector<Edge> next_edges = graph.next(start);
    for(Edge &edge : next_edges){
        if(!graph.vertice[edge.to].visited){
            dfs(edge.to, graph);
        }
    }
}
```