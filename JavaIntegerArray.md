# Integer[] -> int[]

```java
Integer[] a = {1, 2, 3, 4};

// 1. mapToInt에 메서드 참조를 이용하는 방법
int[] b =  Arrays.stream(a).mapToInt(Integer::intValue).toArray();

// 2. mapToInt에 람다식을 이용하는 방법 
int[] c = Arrays.stream(a).mapToInt(i -> i).toArray();
```

# int[] -> Integer[]

```java
int[] a = {1, 2, 3, 4};
Integer[] b = Arrays.stream(a).boxed().toArray(Integer::new);
```

# 출처
https://pangtrue.tistory.com/276