# dijkstra

``` c++
void dijkstra(long long vertex_id, Graph &graph){
    auto compare = [](Vertex a, Vertex b) {
        // distance 降順
        if(a.distance > b.distance){
            return true;
        }else if(a.distance < b.distance){
            return false;
        }else{
            if(a.id < b.id){
                return true;
            }else if(a.id > b.id){
                return false;
            }else{
                return false;
            }
        }
    };
    priority_queue<Vertex, vector<Vertex>, decltype(compare)> pq {compare};
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

### how to use
``` c++
graph.init_vertex();
graph.vertice[start].distance = 0;
dijkstra(start, graph);
```
