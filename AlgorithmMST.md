# 최소 신장 트리
- 가중치의 합이 최소가 되는 최소 연결 부분 그래프 구하기
    ```java
    /**
    * Kruskal 알고리즘 : 간선 선택 기반(그리디)
    * 1. 그래프의 간선을 가중치 오름차순으로 정렬
    * 2. 사이클을 형성하지 않는 가장 낮은 가중치부터 선택
    * 3. 해당 간선을 MST 집합에 추가(union-find 알고리즘)
    */
    import java.util.Arrays;
    import java.util.ArrayList;
    import java.util.Collections;
    import java.util.Comparator;

    class Solution {
        static int parents[];
    
        static int find(int x) {
		    if(parents[x] < 0) return x;
		    return parents[x] = find(parents[x]);
	    }
	
	    static boolean union(int x, int y) {
		    x = find(x);
		    y = find(y);
		    if(x!=y) { 
			    parents[y] = x;
			    return true;
		    }
		    return false;
	    }
    
        public static void main(String[] args) {
            int len; // 간선 길이
            ArrayList<int[]> edges = new ArrayList<int[]>();
		    parents = new int[len + 1];
		
            /** 
            * [정점1, 정점2, 가중치] 전부 삽입
            * Edge를 클래스로 생성하는 방법도 있음
            * 이 경우 compare를 클래스 내부 메서드로 재정의
            * PriorityQueue 사용가능
            */
		
		    Collections.sort(edges, new Comparator<int[]>() {
			    @Override
			    public int compare(int[] o1, int[] o2) {
				    return Integer.compare(o1[2], o2[2]);
			    }
		    });
		
		    Arrays.fill(parents, -1);
		
            // cnt가 간선 개수(정점 개수-1)이 될때까지 union-find 진행
		    int cnt = 0;
		    for(int i = 0; i < edges.size(); i++) {
			    if(union(edges.get(i)[0], edges.get(i)[1])) {
				    if(answer<edges.get(i)[2]) answer = edges.get(i)[2];
				    cnt++;
			    }
			    if(cnt == len-1) break;
		    }
        }
    }
    ```

    ```java
    /**
    * Prim 알고리즘 : 정점 선택 기반
    * 1. 최소에 시작 정점이 MST 집합에 포함
    * 2. MST 집합에 인접한 정점 중 가장 낮은 가중치 선택
    * 참조 : https://toastfactory.tistory.com/184
    */
    import java.util.PriorityQueue;
    import java.util.ArrayList;

    class Solution {
        static class Edge implements Comparable<Edge> {
            int node;
            int w;

            public Edge(int node, int w) {
                this.node = node;
                this.w = w;
            }

            @Override
            public int compareTo(Edge o) {
                return Integer.compare(this.w, o.w);
            }
        }

        public static void main(String[] args) {
            // 자바에서 PriorityQueue는 기본 MinHeap
            int V; // 정점 개수
            PriorityQueue<Edge> pq = new PriorityQueue<>();
            boolean[] visited = new boolean[V];
            // 각 정점에서 다른 정점에 대한 가중치가 들어있는 리스트
            ArrayList<ArratList<Edge>> graph;

            pq.add(new Edge(0, 0));

            while(!pq.isEmpty()) {
                Edge edge = pq.poll();

                if(visit[edge.node]) continue;
                visit[edge.node] = true;
                
                for(Edge next : graph.get(edge.node)) {
                    if(!visit[next.node]) {
                        pq.add(next);
                    }
                }

                if(++cnt==V) break;
            }
        }
    }
    ```

- 가장 긴 간선이 최소가 되게 하는 경우
    이 경우 MST 사용하려면 왜 사용 가능한지 이유 알아야 함