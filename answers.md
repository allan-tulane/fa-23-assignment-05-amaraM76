# CMPS 2200 Assignment 5
## Answers

**Name:**__Amara Midouhas_______________________






- **1a.** It would be logd N . D represents the number of children each internal node has. 


- **1b.** The delete min would be O(logd n) because it can go through the entire tree so the work is proportional to the depth of the tree. For the insert it would be O(logd n) because it has the potential to go up through the tree so the work is proportional to the depth of the tree.


- **1c.** Since the delete -min and insert is O(logd N). For the Dijkstra algorithim, the setup operations like setting each distance for the vertex to infinity and initializing priority que and heap, it will be O(V) because it depends on the number vertices. Then since for delete-min we are working with vertex and the depth of the tree it would be O(V logd V). Then for the insert operation since we can have multiple decrease key operations for each edge and that the work is proportional to the depth of the heap it will be O(E logd V). So together it is O((V+E)logd V).

- **1d.** Since work is O((V+E)logd V):
    - we put |E|= V^1+e in O((V+E)logd V) so O((V+V^1+e)logd V) 
    - we want to find a d so the work becomes O(|E|) so O((V+V^1+e)logd V) = O(V^1+e logdV)
    - we want logdV to be proportional to V^e so then they will grow at a similar rate and it will be O(|E|) so
        logdV = V^e : logV/logd = V^e : d = V^1/e
    - so d needs to be proportional to V^1/e


- **2a.** 
APSP(i,j,k)=min(APSP(i,j,k−1),APSP(i,k,k−1)+APSP(k,j,k−1))

for k=0: 
APSP(0,0,0)= 0 dont go anywhere
APSP(1,0,0) = infinity no direct edge path
APSP(2,0,0) = infinity no direct edge path
APSP(0,1,0) = -3  edge 0 to 1 which is -3
APSP(1,1,0)= 0 stay at vertex 1 
APSP(2,1,0) = infinity no direct edge path
APSP(0,2,0) = 8 edge 0 to 2 to 0 which is 4+4
APSP(1,2,0) = infinity no direct edge path
APSP(2,2,0)= 0 stay at vertex 2 

same for k=1:
APSP(1,2,1) = 1 edge to 2 to edge 1 so 4+4 =8
APSP(0,1,1) = -3  

k=2:
APSP(0,2,2)=min(APSP(0,2,1),APSP(0,1,1)+APSP(1,2,1)) = 8-3 = 5 
APSP(1,2,2)=min(APSP(1,2,1),APSP(1,1,1)+APSP(1,2,1)) = 2+0 =2 


- **2b.** Yes because  APSP(i,j,2)  is the minimum of APSP(i,j,1)and  APSP(i,2,1) + APSP(2,j,1) - as shown above k=2 depends on k=1 and k=0



- **2c.**  APSP(i,j,k-1) and APSP(i,k,k-1) + APSP(k,j,k-1) . so when k>0, we get the shortest path by going the vertices going from 0 to k-1. 

- **2d.** So when it sees a subproblem for the first time, it will compute and store the data in an array. So now when you encounter it again, since its already stored, it can grab it and it doesnt need to be computed to help with redudancy. So the complexity is O(n^3) since of the 3 loops. One for k,i, and j

- **2e.** The work for Johnson is O(|V|⋅|E|log|E|) and for ours is O(n^2). Use Johnson when there are fewer edges because it uses Dijkstra's algorithim. Ours is better for when there are a lot of edges where the max is our work n^2



- **3a.** Yes because MST includes the edge with the max weight and since MMET is the minimum possible max weight so MST is a solution to MMET

- **3b.** starting with any  vertex , you can use a priority que which will select the minimum weight edge at each step and it will do this till all vertices are included . Then it will return the next best tree 


- **3c.** it would be O(ElogV) because for the priority its O(Log V )and that it will run till the total number of edges is used O(E) 
