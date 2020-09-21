# 狄克斯特拉算法

## 1.算法思想

一边遍历一边存储相邻节点的代价值（这个代价值可以是两点之间的距离，也可以是节点本身的代价）

## 2.Python描述

```Python
def find_lowest_cost_node(costs):
    lowest_cost = float("inf")
    lowest_cost_node = None
    for node in costs:
        cost = costs[node]
        if cost < lowest_cost and node not in processed:
            lowest_cost = cost
            lowest_cost_node = node
            
    return lowest_cost_node

graph = {}

# 起点
graph["start"] = {}
graph["start"]["a"] = 6
graph["start"]["b"] = 2

# 节点a
graph["a"] = {}
graph["a"]["fin"] = 1

# 节点b
graph["b"] = {}
graph["b"]["a"] = 3
graph["b"]["fin"] = 5

# 终点
graph["fin"] = {}

# 创建开销
infinity = float("inf")#无穷大
costs = {}
costs["a"] = 6
costs["b"] = 2
costs["fin"] = infinity

# 创建父节点的散列表
parents = {}
parents["a"] = "start"
parents["b"] = "start"
parents["fin"] = None

#存储处理过的节点
processed = []

node = find_lowest_cost_node(costs) #在未处理节点中找出开销最小的节点
while node is not None:
    cost = costs[node]
    neighbors= graph[node]
    for n in neighbors.keys():#遍历当前节点的所有邻居
        new_cost = cost + neighbors[n]
        if costs[n] > new_cost:
            costs[n] = new_cost
            parents[n] = node
            
    processed.append(node)
    node = find_lowest_cost_node(costs)
        
```



## 3.C++代码实现

