# Comparator를 활용해 자료구조 내의 compare 재정의
- 존재하는 data type

    ```java
    // 자료구조 선언하면서 compare를 재정의합니다.
    PriorityQueue<Integer> maxheap = new PriorityQueue<Integer>(new Comparator<Integer>(){
        @Override
        public int compare(Integer o1, Integer o2){
            return o2-o1;
        }
    });
    ```

- custom data type

    ```java
    // 임의의 자료구조 Edge를 정의하면서 comapareto도 재정의합니다.
    public static class Edge implements Comparable<Edge>{
	    int node;
	    int weight;
	    
	    public Edge(int node, int weight){
	        this.node = node;
	        this.weight = weight;
	    }
	    
	    @Override
	    public int compareTo(Edge o){
	        return this.weight-o.weight;
	    }
	}
	
	public static void main(String[] args){
		PriorityQueue<Edge> pq = new PriorityQueue<Edge>();
    }
    ```
