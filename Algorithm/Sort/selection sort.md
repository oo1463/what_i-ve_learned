# 선택정렬 (selection sort)

- 배열에서 해당 자리를 선택하고 그 자리에 오는 값을 찾는 것


1. 주어진 배열 중에 최소값을 찾는다.
2. 그 값을 맨 앞에 위치한 값과 교체한다. (pass)
3. 맨 처음 위치를 뺀 나머지 배열을 같은 방법으로 교체한다.

```
void selectionSort(int[] arr) {
    int indexMin, temp;    
    for (int i = 0; i < arr.length-1; i++) {        // 1.
        indexMin = i;
        for (int j = i + 1; j < arr.length; j++) {  // 2.
            if (arr[j] < arr[indexMin]) {           // 3.
                indexMin = j;
            }
        }
        // 4. swap(arr[indexMin], arr[i])
        temp = arr[indexMin];
        arr[indexMin] = arr[i];
        arr[i] = temp;
    }
     
    //print(Arrays.toString(arr));
}
```

## 시간복잡도
- 최선 : O(n^2)
- 평균 : O(n^2)
- 최악 : O(n^2)

## 공간복잡도
O(n)


## 장점

- 알고리즘이 단순
- swap 자체는 많이 일어나지는 않음


## 단점

- 시간복잡도가 커 비효율적
- 불안정 정렬
  
