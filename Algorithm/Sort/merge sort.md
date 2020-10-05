# 병합 정렬 (merge sort)

- 분할정복 알고리즘 기법을 사용

- 요소를 모두 쪼갠 후 다시 합병시키면서 정렬 해 나가는 방식


```
void merge(int left, int right)
{
	int mid = (left + right) / 2;

	int i = left;
	int j = mid + 1;
	int k = left;
	while (i <= mid && j <= right)
	{
		if (arr[i] <= arr[j]) 
			arr2[k++] = arr[i++]; 
		else
			arr2[k++] = arr[j++];
	}

	int tmp = i>mid ? j : i;
	
	while(k<=right) arr2[k++] = arr[tmp++];

	for (int i=left;i<=right;i++) arr[i] = arr2[i];
}

void merge_sort(int left,int right)
{
	int mid;
	if (left < right)
	{
		mid = (left + right) / 2; 
		merge_sort(left, mid);
		merge_sort(mid + 1, right);
		merge(left, right);
	}
}
``` 

- 합병정렬은 순차적인 비교로 정렬을 진행하므로, LinkedList의 정렬이 필요할 때 사용하면 효율적이다.

## 시간복잡도

- 최선 : O(nlog₂n)
- 평균 : O(nlog₂n)
- 최악 : O(nlog₂n)


## 공간복잡도
O(n)


## 장점

- stable 정렬
- 시간복잡도가 O(nlogn)으로 빠른 정렬에 속한다

## 단점

- 퀵소트보다는 느리다
- 힙정렬보다 메모리를 더 많이먹음