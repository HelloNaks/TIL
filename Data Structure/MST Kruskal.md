# MST Kruskal
### MST
> **MST**란, Minimum Spanning Tree의 약자로, 최소 신장 트리라는 뜻을 가진 알고리즘을 의미한다.
> 해당 그래프에서 모든 point들이 edge들로 연결된다고 가정했을 때, 가중치가 가장 짧은 방법을 구하는 알고리즘이다.
> ex) Kruskal(크루스칼) 알고리즘, Prim(프림) 알고리즘
---

### Kruskal(크루스칼)
> **Kruskal**이란, MST의 종류 중 하나로, 모든 정점을 최소 비용으로 연결하는 방법을 구하는 알고리즘이다.
1. 그래프의 간선들의 가중치를 오름차순으로 정렬한다.
2. 정렬된 간선 리스트에서 사이클을 형성하지 않는 간선을 선택한다.
3. 해당 간선을 MST의 집합에 추가한다.
> ex) 백준의 1197번, 1922번, 1647번...

***
#### 자바로 구현한 Kruskal 알고리즘

```java

	static int[] parent;
	static int V;
	static PriorityQueue<Edge> pq;
	public static void main(String[] args) {
		Scanner scann = new Scanner(System.in);
		V=scann.nextInt();
		int E=scann.nextInt();
		parent = new int[V+1];
		for(int i=1;i<V+1;i++) {
			parent[i]=i;
		}
		pq = new PriorityQueue<>();
		
		for(int i=0;i<E;i++){
			int a=scann.nextInt();
			int b=scann.nextInt();
			int c=scann.nextInt();
			pq.add(new Edge(a,b,c));
		}
		
		System.out.println(kruskal());
	}
	private static int kruskal() {
		int ret=0;
		int cnt=0;
		while(!pq.isEmpty()) {
			Edge temp = pq.poll();
			int a=find(temp.from);
			int b=find(temp.to);
			if(a==b) {
				continue;
			}
			union(a, b);
			
			ret += temp.val;
			if(++cnt==V) {
				break;
			}
		}
		return ret;
	}
	public static int find(int a) {
		if(a==parent[a]) {
			return a;
		}
		return parent[a]=find(parent[a]);
	}
	
	public static void union(int a, int b) {
		int tempa = find(a);
		int tempb = find(b);
		if(tempa==tempb) {
			return;
		}
		parent[b]=a;
	}
	public static class Edge implements Comparable<Edge> {
		int from;
		int to;
		int val;
		public Edge(int from, int to, int val) {
			this.from=from;
			this.to=to;
			this.val=val;
		}
		@Override
		public int compareTo(Edge o) {
			return Integer.compare(this.val, o.val);
		}
	}
}
```


