# dijkstra
!!! Note
    未検証
``` c++
void dijkstra(long long vertex_id, Graph &graph){
    priority_queue<Vertex> pq;
    pq.push(graph.vertice[vertex_id]);

    while(!pq.empty()){
        Vertex vertex = pq.top();
        pq.pop();

        vector<Edge> next_edges = graph.next(vertex);
        for(Edge &edge : next_edges){
            if(graph.vertice[edge.to].distance > vertex.distance + edge.weight){
                graph.vertice[edge.to].distance = vertex.distance + edge.weight;
                pq.push(graph.vertice[edge.to]);
            }
        }
    }
}
```
