# bfs
!!! Note
    未検証
``` c++
void dfs(long long vertex_id, Graph &graph){
    queue<Vertex> q;
    q.push(graph.vertice[vertex_id]);

    while(!q.empty()){
        Vertex vertex = q.front();
        q.pop();
        graph.vertice[vertex.id].visited = true;

        vector<Edge> next_edges = graph.next(start);
        for(Edge &edge : next_edges){
            if(!graph.vertice[edge.to].visited){
                graph.vertice[edge.to].visited = true;
                graph.vertice[edge.to].distance = vertex.distance + edge.weight;
                q.push(graph.vertice[edge.to]);
            }
        }
    }
}
```