# Java 배열 정렬
```java
Arrays.sort(T[] a, int fromIndex, int toIndex, Comparator<? super T> c);
```
- 오름차순 정렬
    ```java
    int[] arr = {6,3,2,1,5};
    String[] arr2 = {"h", "e", "a", "c"};
    Arrays.sort(arr);   // {1, 2, 3, 5, 6}
    Arrays.sort(arr2);  // {"a", "c", "e", "h"}
    ```
- 내림차순 정렬
    - String
        ```java
        Arrays.sort(arr2, Collections.reverseOrder());  // {"h", "e", "c", "a"}
        ```
    - int : Integer 타입으로 변경
        ```java
        Integer[] arr3 = Arrays.stream(arr).boxed().toArray(Integer[]::new);
        Arrays.sort(arr3, Collections.reverseOrder());  // {6, 5, 3, 2, 1}
        ```
- 출처 : https://velog.io/@ju_h2/JAVA-int-String-%EB%B0%B0%EC%97%B4%EC%9D%98-%EC%98%A4%EB%A6%84%EC%B0%A8%EC%88%9C-%EB%82%B4%EB%A6%BC%EC%B0%A8%EC%88%9C-%EC%A0%95%EB%A0%AC