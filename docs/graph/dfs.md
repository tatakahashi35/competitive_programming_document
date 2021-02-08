# dfs

``` c++
void dfs(long long vertex_id, Graph &graph){
    graph.vertice[vertex_id].visited = true;
    Vertex start = graph.vertice[vertex_id];

    vector<Edge> next_edges = graph.next(start);
    for(Edge &edge : next_edges){
        if(!graph.vertice[edge.to].visited){
            graph.vertice[edge.to].distance = start.distance + edge.weight;
            dfs(edge.to, graph);
        }
    }
}
```